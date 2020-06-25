---
title: Statistical Functions
keywords: Statistical Functions
sidebar: forlang_sidebar
permalink: formula-language/statistical-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---

# Statistical Functions


## AVERAGE

Calculates an average (arithmetic mean) for a series of numbers.


**AVERAGE (value1, value2, ...)**

Value1, value2, ... are one or more numeric values or references to numeric values. An average (arithmetic mean) is calculated by taking the sum of all values, and dividing by the number of values.

Each value is equally weighted. To obtain a weighted average, you can multiply each value by a weight in the expression.

  **AVERAGE([Value1] * [Weight1], [Value2] * [Weight2], [Value3]* [Weight3])**


## COUNT

Counts how many cells have numeric or date/time values.

**COUNT (Value1, Value2, ..., ValueN)**

Value1, value2, ... valueN can be references to different data structures, such as columns. Each numeric or date/time value is counted. Empty, error, boolean or text values that are not convertible into numeric values are not counted.

When a reference is a range reference, only those numeric and date/time values within the range will be counted.


## MAX

Gives you the largest numeric value out of a series.

**MAX (Value1, value2, ..., valueN)**

Value1, value2, ... valueN are any number of numeric values or references to numeric values from which you want the maximum value found. Arguments may be numbers, boolean values, text values convertible into numbers, or empty. Error values and text values that are not convertible into numbers will produce an error.

When the argument list is empty, MAX () returns zero.


## MEDIAN

Calculates the median value of a specified list of numeric values.

**MEDIAN (Value1, value2, ..., valueN)**

Value1, value2, ..., valueN are any number of numeric values or references to numeric values for which you want the median value found. If any argument is an error value, or there are no numeric values within the series of arguments, then MEDIAN () will return an error value.

The median is the middle value of the sorted list of numeric values (you do not need to sort Value1, value2, ..., valueN prior to passing them to the MEDIAN () function). When the list contains an odd number of values, the median will be the value at position CEIL(N/2). For example, the median of the 5-value list 0, 20, 30, 50, 80, is the value in the third position: 30. When the list contains an even number of values, the median will be the average of the two values in the middle. For example, the median of the 4-value list 7, 20, 30, 45, is the average of the two middle elements (20 and 30): 25. Note that the value of the MEDIAN () varies most from the arithmetic mean of the sorted list when the distribution of values tends to favor one side or the other of that arithemtic mean. For example, the arithmetic mean of the 5-value list 1, 2, 3, 21, 43 is 14 but it's median value is 3.


## MIN

Gives you the smallest numeric value out of a series.

**MIN (Value1, value2, ..., valueN)**

Value1, value2, ... valueN are any number of numeric values or references to numeric values from which you want the minimum value found. Arguments may be numbers, boolean values, text values convertible into numbers, or empty. Error values and text values that are not convertible into numbers will produce an error.

The minimum value for a series of numbers can be its largest magnitude negative number because larger magnitude negative numbers are less than smaller magnitude negative numbers. For example, given the expression MIN ( -1500, -50, 5, 150), the return value is -1500 and not 5. To determine the numeric value with the smallest magnitude you would use the ABS () function on each argument. The following example would produce a minimum value of 5.

**MIN (ABS (-1500), ABS (-50), ABS (5), ABS (150))**

When the argument list is empty, MIN () returns zero.

**MAX ()**


## STDEV

Calculates an approximate standard deviation of a specified sampling of numeric values.

**STDEV (Value1, value2, ..., valueN)**

Value1, value2, ..., valueN are any number of numeric values or references to numeric values that you've given to provide a sample space of your data set. If any value contains an error, then the function evaluates to the first error encountered. An error value is returned if the sample space contains no numeric values.

The standard deviation is used in statistical studies to make inferences about a larger population of data based on sampling only a subset. For well-chosen samplings, a small standard deviation indicates most data points tend to cluster within a narrow range of values. A larger standard deviation indicates greater variability in the data points, and that there is a higher likelihood for values to occur farther away and/or more frequently away from the expected norm.


## VAR

Calculates the estimated variance for a specified sampling of numeric values.

**VAR (Value1, value2, ..., valueN)**

Value1, value2, ..., valueN are any number of numeric values or references to numeric values you provide to specify a sampling of your larger data population. If any argument contains an error value or there are no numeric values in the sampling, the VAR () function evaluates to the first error value it encounters.

Variance is a measure of statistical variability, and is used in statistical studies based on small samplings from much larger data populations to draw inferences about the variability of those data populations.
