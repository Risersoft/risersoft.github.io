---
title: Map Expression
keywords: Map Expression
sidebar: edp_sidebar
permalink: easy_data_porter/map-expression.html
folder: EDP
hide_sidebar: false
comments: false
---

# Map Expression

The map expression follows Excel formula language syntax and supports almost all of Excel functions. Some functions have been provided to facilitate access to data. These are:

|Function|Description|
|--------|------------|
|SourceField(“fieldname”)|Provides access to source data for the row currently being processed.|
|TargetField(“fieldname”)|Provides access to target data for the row currently being processed. 
This function allows you to access target field for which transformation has already been defined.|

 

You can enter the map expression in following ways:

1.  Enter manually or copy/paste from elsewhere.

 

2.  Click the drop down button shown next to the cell and select from a pre-defined list. You can use this if the target field is a simply mapping to a source field or to select a starting expression.

 

3.  Select the “Build Expression …” from the drop down list. This will open up the formula builder.

![](/images/formulabuilder.jpg)

The formula builder lists the functions on the left, in a neatly categorized view. You can select any function to view its description in the bottom left portion.

 

If you double click a function, a function builder box is displayed:

![](/images/functionbuilder.jpg)

This dialog lists the parameters of the function and displays a description of the selected argument. You can enter the values and then select OK to update the formula builder.

 

The formula builder displays the status of the expression currently entered and whether the syntax is OK.

 

When you press OK, the map expression is updated and the sample target data is changed as per the new expression. This gives an instant feedback to the user.