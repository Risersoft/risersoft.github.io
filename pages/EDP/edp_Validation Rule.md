---
title: Validation Rule
keywords: Validation Rule
sidebar: edp_sidebar
permalink: easy-data-porter/validation-rule.html
folder: EDP
hide_sidebar: false
comments: false
---

# Validation Rule

A validation rule is defined allows you to define a validation expression to check data. This rule can be defined for both source and target data. You write an expression which evaluates to true or false. You choose an action to be taken if the validation expression is false – reject that particular row or terminate the transformation.

 

You can use the Field(“fieldname”) function to access data. This function will provide source data during source validation and target data during target validation and hence can be used in both source and target schemas.

**Examples**

|Field(“F1”)=2|The value of F1 Field should be 2|
|Len(Field(“F2”))>0|The length of data in F2 Field should be > 0|

 

You can define multiple validation rules for a recordtype. All validation rules will be checked in the order defined.