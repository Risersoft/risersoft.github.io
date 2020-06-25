---
title: Information Functions
keywords: Information Functions
sidebar: forlang_sidebar
permalink: formula-language/information-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---


# Information Functions

## ISEVEN

Returns TRUE if the specified value is an even number.


**ISEVEN(value)**

Value is a number thought to be even (divisible by the integer 2.) A value that is not an integer will first be converted to an integer using the FLOOR function before evaluation.



## ISNONTEXT

Returns TRUE if the specified value refers to any not-text value.


**ISNONTEXT(value)**

Value is an object or the result of an expression evaluation that you want to test to determine whether it is a text value (such as a .NET String object) or a non-text value.



## ISNUMBER

Returns TRUE if the specified value refers to a numeric value.



**ISNUMBER(value)**

Value is an object or the result of evaluating an expression that you want to test to determine whether it is a number or not. A numeric value can be an integer, floating-point or decimal number.

## ISODD

Returns TRUE if the specified value is an odd number.


**ISODD(value)**

Value is a number thought to be odd (not divisible by the integer 2.) A value that is not an integer will first be converted to an integer using the FLOOR function before evaluation.



## ISTEXT

Returns TRUE if the specified value refers to a text (or string) value.



**ISTEXT(value)**

Value is an object or the result of evaluating an expression that you want to test to determine whether it is of a text (e.g., string) value or a non-text value (which could be a numeric, boolean, or error value.)



## INFO

Returns information about the current operating environment.


**INFO(type)**

Type is a string indicating the type of information to return.

"directory" = The full path to the current folder. "osversion" = The currently operating system version as a string. "system" = The current operating system. This will always return "pcdos" which indicates Microsoft Windows. The corresponding function in Excel can also return "mac" for Macintosh, but since UnitCAD is only supported in Windows, this function will always return "pcdos".

The following are supported by Microsoft Excel, but have no correlation in UnitCAD: "numfile", "origin", "recalc", "release".

The following are supported in older versions of Excel, but not Office2007, and have no correlation in UnitCAD: "memavail", "memused", "totmem".


## N

Converts a value to a number.


**N(value)**

Value is the value to be converted to a number. The following are acceptable values:

A number - returns the number. A date - returns the date. True - returns 1. False - returns 0. An error value - returns the error value. Any other value - returns 0.
