---
title: "Who Moved My Cheese – A Practical guide to porting from Asp .Net MVC to Asp .Net Core"
published: true
permalink: who-moved-my-cheese-porting-from-asp-net-mvc-to-asp-net-core5.html
tags: [blog]
---

![](/images/cheese.jpg)

## Introduction

With the announcement of .Net 5 by Microsoft, finally there is only one current version of .Net. The old .Net framework won’t be updated and all new development would happen only in the new .Net 5 codebase.

That leaves apps based on .Net MVC with no choice but to upgrade. While there is no hurry, it is prudent that the porting happens soon to take advantage of the new updates. 

-	Immo Landswerth stated in his [presentation](https://www.youtube.com/watch?v=bvmd2F11jpA&list=PLdo4fOcmZ0oVWop1HEOml2OdqbDs6IlcI&index=7) at DotnetConf 2020 that during the porting project, click stops must be used – this means having working code at all times that builds and preferably can be tested and published. 

-	There is another thing we should add to this – **code reuse**. 

      o	 This means that the classes and the views be reused in the old Asp .Net MVC project and the new Asp .Net Core 5 project. 
	  
      o	 This is especially important in bigger solutions (>25+ projects) where the conversion process is likely to take months - sometimes years – rather than days. 
	  
      o	 Code reusability means less code has to be maintained during the entire conversion journey and beyond.

-	This guide puts focus on conversion with code reuse. On the internet there are several resources that go in detail about Asp .net Core but this topic is not adequately covered.

## Project Frameworks

-	Use .Net Standard 2.0 for sharing code between .Net framework and .Net 5. 

-	Conversion should ideally be started at the bottom of dependency graph ie base libraries and they should be converted to .Net Standard 2.0 so that those projects can be made ready for sharing.

-	Where a class or function is not available in .Net standard, consider making an interface which is implemented by a higher level class based on .Net 4.x or .Net 5.

-	If the project cannot be converted to .Net Standard, can have following options for the new project that is based on .Net 5:

     o	Same code files but different project in-place
	 
     o	Same code files called by “Add to Link” in .Net 5 project
	 
     o	Different code files and project with same output file name and namespace.
	 
	 
The exact option chosen for a particular project depends on the classes in it. As a best practice, there should be at least one library project that is specific for each framework. In this project, framework specific controller base classes and helper methods are defined.

## Controllers

To reuse controller code, it is important to have base classes for MVC and API Controllers. Then the controller classes in the apps can inherit from these base classes irrespective of which project they are called in. These base classes can also help to bring uniformity across the two frameworks so that downstream class code can remain same.

Controller.Initialize method is no longer available in any of the controller classes. Consider using attribute filters or implement filters on the controller class. Initialize method code can be moved to the constructor or to OnActionExecuting method.

**a.	MVC Controller**

  *i.	Inherit from Controller* 
  
Implement IResultFilter and IExceptionFilter if OnResultExecuting, OnResultExecuted or OnException methods were used earlier.
 
 *ii.	ActionResult*
 
ActionResult models are mostly same as earlier with different namespace. To enable code reuse, can define own results as POCO classes and then have the controller base convert them to platform specific models.

**b.	API Controller**

  *i.	Inherit from ControllerBase. Implement IActionFilter, IResultFilter and IExceptionFilter if OnActionExecuting, OnActionExecuted,  OnResultExecuting, OnResultExecuted or OnException methods were used earlier.*

 *ii.	IHttpActionResult -> IActionResult*

Can define a dummy interface to enable code reuse:
		
```
public interface IHttpActionResult : IActionResult
{
}

```

 *iii.	HttpResponseException*

In Asp .Net MVC, following code anywhere in the action code would create an Exception Response
		
```		
                    Throw New 
					
HttpResponseException(actionContext.Request.CreateErrorResponse(HttpStatusCode.Unauthorized, oRet.Message))
					
```


In Asp .Net Core, to achieve the same effect, HttpResponseFilter would need to be implemented as per [this](https://docs.microsoft.com/en-us/aspnet/core/web-api/handle-errors?view=aspnetcore-3.1) link.
		
		

## Security

In Asp .Net MVC, Owin/Katana was introduced during later versions. In Asp .Net core, this is fully absorbed into the core framework. So OwinContext can generally be replaced by HttpContext. To enable code reuse, one can define an interface like below
	
```	
	
   public interface IOwinHelper
    {
        Task<ClaimsIdentity> SigninJwt(IHostedController controller, string AccessToken, string AuthenticationType);

        RSIdentity TicketIdentity(RSHostedAppInfo info, string jwtToken, bool IgnoreExpiry);

        Task<string> Logout(IHostedController controller);

    }
	
```	
	

This interface can have implementations in both frameworks and then the upstream classes and reuse code.

Frequently, cookie and bearer authentication is added to the project and integrated with any Identity as a service provider like Auth0, Okta or SaasMatter. For things like session or custom validation, CookieAuthenticationProvider class is inherited and added while provisioning cookie authentication. The same can be achieved by using CustomCookieAuthenticationEvents in Asp .Net Core.

## Logging

In Asp .net MVC, generally external logging providers like Serilog or NLog were used. These were configures so as to split logging on a per-background task or per-request basis. Now Asp .Net core has built-in support for logging from the namespace Microsoft.Extensions.Logging. However, this mechanism does not support logging to files and for those one still has to use the 3rd party loggers, which provide a mechanism to hook onto the built in logging provider.

Sample code earlier for Serilog

```

var Log = new LoggerConfiguration().WriteTo.File(filePathFormat, rollingInterval: RollingInterval.Day, rollOnFileSizeLimit: true, fileSizeLimitBytes: 10485760, retainedFileCountLimit: 101).WriteTo.Trace(outputTemplate).CreateLogger();
                return Log;
				
```			
				
				

Sample code now for use of Serilog with Microsoft.Extensions.Logging

```

var Log2 = new LoggerConfiguration().WriteTo.File(filePathFormat, rollingInterval: RollingInterval.Day, rollOnFileSizeLimit: true, fileSizeLimitBytes: 10485760, retainedFileCountLimit: 101).WriteTo.Trace().CreateLogger();
            using (var Factory = LoggerFactory.Create(builder => builder.AddSerilog(Log2)))
            {
                log = Factory.CreateLogger<IProviderContext>();
            }
			
```			
			

## Configuration aka Settings

This is one of the major changes in Asp .Net Core. Web.Config has been done away with and BindingRedirects are no longer required – this is one of the major attractions of the new framework.

In Asp .Net MVC, frequently Configuration.AppSettings is used anywhere in the code. Further, sometimes a custom section is added to web.config and the custom settings file placed in App_data folder which can be conveniently excluded during deployment.

```

<configSections>
    <sectionGroup name="rsmx">
      <section name="settings" type="risersoft.shared.cloud.ConfigSectionHandler, risersoft.shared.cloud" allowLocation="true" allowDefinition="Everywhere" />
    </sectionGroup>
  </configSections>

<rsmx>
    <settings configSource="app_data\sitesettings.config" />
  </rsmx>
  
```  

To handle above scenario, it is best to move to newer IConfiguration in old and new solutions.  For doing so, one may write a custom binder as follows:

```

public class XMLConfigProvider : ConfigurationProvider, IConfigurationSource
{
    public override void Load()
    {
        foreach (ConnectionStringSettings connectionString in ConfigurationManager.ConnectionStrings)
            System.Data.Add($"ConnectionStrings:{connectionString.Name}", connectionString.ConnectionString);

        foreach (var settingKey in ConfigurationManager.AppSettings.AllKeys)
            System.Data.Add(settingKey, ConfigurationManager.AppSettings(settingKey));

        clsCollecString<clsCollecString<string>> settings = ConfigurationManager.GetSection("rsmx/settings");
        foreach (var kvp1 in settings)
        {
            foreach (var kvp2 in settings(kvp1.Key))
            {
                var setting = myUtils.cStrTN(settings(kvp1.Key).TryValue(kvp2.Key));
                System.Data.Add("rsmx:" + kvp1.Key + ":" + kvp2.Key, setting);
            }
        }
    }

    public IConfigurationProvider Build(IConfigurationBuilder builder)
    {
        return this;
    }
    public static IConfiguration CreateConfig()
    {
        var builder = new ConfigurationBuilder();
        var config = builder.Add(new XMLConfigProvider()).Build;
        return config;
    }
}

```

And then set somewhere as a global variable. Replace ConfigurationManager.AppSettings by something like GlobalModule.Configuration, and then code classes can be reused.

## Bundling and Minification


ScriptsBundle and StylesBundle are no longer supported and instead now Json based bundle configuration has been introduced. In Asp .Net MVC projects, Scripts.Render and Styles.Render is generally freely used in views. To enable code reuse, we can write an HTMLHelper extension like below, which is callable from both frameworks.

```

public IHtmlString RenderJsCss(this HtmlHelper helper, bool useCDN, params string[] arrBundle)
{
    List<IHtmlString> lst = new List<IHtmlString>();
    foreach (var bundleid in arrBundle)
    {
        switch (bundleid.Trim().ToLower())
        {

            case "jquery":
                {
                    lst.Add(new HtmlString($"<script src = ""/scripts/jquery-3.4.1.js"" ></script>"));
                    lst.Add(new HtmlString($"<script src = ""/scripts/jquery-ui.js"" ></script>"));
                    lst.Add(new HtmlString($"<script src = ""/scripts/jquery.ui-contextmenu.js"" ></script>"));
                    lst.Add(new HtmlString($"<link href = ""/Content/jquery-ui.css"" rel=""stylesheet"" />"));
                    break;
                }

            case "angular":
                {
                    lst.Add(new HtmlString($"<script src = ""/scripts/angular.js"" ></script>"));
                    lst.Add(new HtmlString($"<script src = ""/scripts/angular-sanitize.js"" ></script>"));
                    lst.Add(new HtmlString($"<script src = ""/scripts/angular-spinner.min.js"" ></script>"));
                    break;
                }

            case "bootstrap":
                {
                    lst.Add(new HtmlString($"<script src = ""/scripts/bootstrap.js"" ></script>"));
                    lst.Add(new HtmlString($"<script src = ""/scripts/respond.js"" ></script>"));
                    lst.Add(new HtmlString($"<link href = ""/Content/bootstrap.css"" rel=""stylesheet"" />"));
                    lst.Add(new HtmlString($"<link href = ""/Content/font-awesome.css"" rel=""stylesheet"" />"));
                    break;
                }

            case "rs":
                {
                    lst.Add(new HtmlString($"<script src = ""/scripts/rsweb.js"" ></script>"));
                    lst.Add(new HtmlString($"<script src = ""/scripts/rsang.js"" ></script>"));
                    lst.Add(new HtmlString($"<link href = ""/Content/site.css"" rel=""stylesheet"" />"));
                    lst.Add(new HtmlString($"<link href = ""/Content/rsweb.css"" rel=""stylesheet"" />"));
                    break;
                }
        }
    }
    return lst.Render;
}

```


## HttpContext and HttpRequest

HttpContext.current has been removed, and although there are strategies to circumvent this, it is best to refactor code such that a controller or context is always available. 

HttpRequest.Url has been removed, and if there is code which uses this property, it is best to write an extension method to get it back.

```

public Uri GetUri(this HttpRequest request)
{
    var builder = new UriBuilder();
    builder.Scheme = request.Scheme;
    builder.Host = request.Host.Host;
    builder.Port = request.Host.Port;
    builder.Path = request.Path;
    builder.Query = request.QueryString.ToUriComponent();
    return builder.Uri;
}

```


## Views and Content

**a.	Html (cshtml/vbhtml)**

Bad news - Vbhtml has been removed from new framework.  Good news is that this is not so much of a roadblock. If you have some vbhtml code, start by converting vbhtml to cshtml “in-place” – Asp .net MVC projects support cshtml and vbhtml in one project.

**b.	Content in wwwroot**

Now all static content is put inside the wwwroot folder – so the top level web app has to follow this convention.

Sometimes, embedded views and content is used in Asp .Net MVC using VirtualPathProvider. This project has to be reused by maintaining structure as per wwwroot requirement, and then handling the extra wwwroot path in the virtualpathprovider code.

Asp .Net Core support Razor Class Library (RCL) as first class citizen, and that a much better way to have view and content library going forward.

**c.	HTMLHelper and HTMLTextWriter**

Asp .Net Core introduces TagHelper, but HTMLHelper is still supported. There are some caveats though:

  *i.	The output is IHTMLContent instead of IHTMLString. To enable code reuse, we can write following code:*
  
```  

public interface IHTMLString : IHtmlContent
{
}

```

  *ii.	The extension methods are defined for IHTMLHelper instead of HTMLHelper.*

To enable code reuse, we can write additional code as follows, which calls back the original HTMLHelper based method.

```

public IHTMLString RenderLookup(this IHtmlHelper helper, string TableName, clsFormDataModel model)
{
    return RenderLookup((HtmlHelper)helper, TableName, model);
}

```


In HTML Helper methods, HTMLTextWriter is no longer supported. Instead there are a variety of helper methods in Asp .Net core. To enable code reuse, consider switching to a stringbuilder based implementation, or some library that is based on .Net Standard can also be used.


## Entity Framework

Entity Framework Core 3.1.9 supports .Net standard 2.0 – so consider switching to that in the library projects. Database first workflow can be achieved by using tools like EF Core Power Tools, which generate the model like before.

Often times, the dbcontext partial class is extended for setting the session context for multi tenant applications. The same is still available using code as follows

```

protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
        {

            var connection = new SqlConnection(connectionString);
            connection.StateChange += Connection_StateChange;
            optionsBuilder.UseLoggerFactory(loggerFactory).
                UseSqlServer(connection);
        }


private void Connection_StateChange(object sender, System.Data.StateChangeEventArgs e)
        {

            if (e.CurrentState == System.Data.ConnectionState.Open)
            {
                var senderConnection = (DbConnection)sender;
                senderConnection.SetSessionContext("TenantId", TenantId);
            }
        }
		
```		
		


## Conclusion

Porting of a large Asp .Net MVC solution requires significant amount of planning and refactoring.  We need to choose our strategies wisely and adopt maximum code-reuse with maximum click-stops for successful and timely project completion.
