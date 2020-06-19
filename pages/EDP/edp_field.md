---
title: Field
keywords: Field
sidebar: edp_sidebar
permalink: easy-data-porter/field.html
folder: EDP
hide_sidebar: false
comments: false
---

# Field

All field names must be unique within a recordtype. If you change the name to something which already exists, an error will be dispalayed.

 

If the schema has been defined by connection, Easy Data Porter will display the equivalent client data type of the field. The properties pane will display all the properties given by the provider. These are basically for informational purposes only.

 

If the schema is defined by user, Easy Data Porter will display a list of data types from which selection has to be made. The properties pane will display properties according to the selection made. Following are the data types and properties:

|Data Type|Properties|
|---------|----------|
|Boolean|BooleanFormat|
|DateTime|DateTimeFormat|
|Decimal|NumDecimals, DecimalChar, ThousandsChar|
|Integer|ThousandsChar|
|Text|PadChar, Align|

Following is the description of properties:

|Property|Description|
|---------|-----------|
|DefaultExpr|Default Map Expression for the field. This will be applied whenever the schema is imported.|
|BooleanFormat|Yes/No or True/False|
|DateTimeFormat|A list of some formats is presented. You can select from this list or type your own format.|
|NumDecimals|No. of Digits after the Decimal Point|
|DecimalChar|Decimal Character|
|ThousandsChar|Thousands Character, Default None|
|PadChar|Padding Character, Used if size for text is defined.|
|Alignment|Left, Right or Center|