---
title: Logical Functions
keywords: Logical Functions
sidebar: forlang_sidebar
permalink: formula-language/logical-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---


# Logical Functions

## AND

Logical-AND returns the boolean value, FALSE, if at least one argument has a value of FALSE. When all arguments are TRUE, then this function returns TRUE.


**AND (boolean1, boolean2, ...)**

Boolean1, boolean2, ... are a list of boolean (TRUE or FALSE) values or conditional statements (any expression which itself evaluates to a boolean TRUE or FALSE value) to be evaluated for the constraint that all arguments should be TRUE (or conversely, that at least one argument should be FALSE.)

All arguments are tested (i.e., the logical-AND function does not use "short-circuit" evaluation, in which the function can stop executing as soon as the first argument having the boolean value, FALSE, has been processed.)

This function stops evaluating immediately when any argument results in an error value. An error value is neither TRUE nor FALSE, therefore the return value of the logical-AND function is undefined.


## FALSE

A constant function always returning the FALSE value of Boolean logic.


FALSE () will always evaluate to the boolean value of FALSE. It takes no arguments.

## IF

Chooses between two outcomes (or expressions to evaluate) based on the result of a logical test on a value or expression you specify.


**IF (boolean_test, result_if_true, [result_if_false])**

Boolean_test is a value (or an expression) which the IF function evaluates to produce a boolean value of either TRUE or FALSE. The outcome of this test determines which result will be returned by the function.

Result_if_true is a value (or the outcome of another expression) that will be returned only when boolean_test has evaluated to the boolean value, TRUE.

Result_if_false is a value (or the outcome of another expression) that will be returned only when boolean_test has evaluated to the boolean value, FALSE.

The IF function allows you to write an expression that branches to one expression (when the boolean_test is TRUE) or another (when the boolean_test is FALSE) based on an arbitrary condition you have specified.

The result_if_false is not specified and boolean_test is FALSE, the IF function will return FALSE.

If boolean_test's evaluation produces an error value then neither Result_if_true nor Result_if_false will be evaluated. Instead, the IF function returns the error value from its evaluation of boolean_test.


## NOT

Logical-NOT returns the inverse boolean value of its argument.



**NOT(boolean1)**

Boolean1 is any boolean (TRUE or FALSE) value, or conditional statement (made up of any expression which itself evaluates to a boolean TRUE or FALSE value) to be inverted.

If boolean1 was TRUE, then the Logical-NOT would return FALSE. If boolean1 was FALSE, then the Logical-NOT would return TRUE.

If Boolean1 is an expression that evaluates to an error value, then the result of a Logical-NOT operation is undefined because an error value is neither TRUE nor FALSE.

## OR

Logical-OR returns the boolean value, TRUE, if at least one argument has a value of TRUE. When all arguments are FALSE, then this function returns FALSE.



**OR (boolean1, boolean2, ...)**

Boolean1, boolean2, ... are a list of boolean (TRUE or FALSE) values or conditional statements (any expression which itself evaluates to a boolean TRUE or FALSE value) to be evaluated for the constraint that at least one argument should be TRUE (or conversely, that all arguments should be FALSE.)

All arguments are tested (i.e., the logical-OR function does not use "short-circuit" evaluation, in which the function can stop executing as soon as the first argument having the boolean value, TRUE, has been processed.)

This function stops evaluating immediately when any argument results in an error value. An error value is neither TRUE nor FALSE, therefore the return value of the logical-OR function is undefined.


## TRUE

A constant function always returning the TRUE value of Boolean logic.



TRUE () will always evaluate to the boolean value of TRUE. It takes no arguments.
