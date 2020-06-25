---
title: Math Functions
keywords: Math Functions
sidebar: forlang_sidebar
permalink: formula-language/math-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---

# Math Functions

## ABS

Calculates a number's absolute value.

**ABS(value)**

A number's absolute value is its value without any sign. It represents the magnitude of a value while ignoring its direction (positive or negative) on a number line or vector.

## ACOS

Returns the angle (measured in radians) having the specified value of the trigonometric cosine function.

**ACOS(value)**

Value is the real number result of the cosine function taken of an angle you want to find. The legal values of the cosine function are from -1 to 1. An inverse cosine by default will return the normal angle from 0 up to PI. This is because there are several angles which may have an identical value of their cosine. For example, the angles -PI/2, PI/2, 3PI/2, etc., all have a cosine of zero. You can find alternate angles by adding (or subtracting) any multiple of PI radians to the normal angle returned by the inverse cosine function.

You can convert the result of the inverse cosine function from radians into degrees by multiplying it by 180/PI ().


## ACOSH

Returns the angle (measured in radians) having the specified value of its hyperbolic cosine function.

**ACOSH(value)**

Value is the hyperbolic cosine of some angle (measured in radians) that you want to find. As you might expect, the values of the hyperbolic cosine function (see the [COSH]() function) increase at a hyperbolic rate, but one consequence is that these ever larger changes in the hyperbolic cosine will correspond to ever smaller changes in the angle. This relationship is intrinsic to many of the mathematical and engineering applications of the inverse hyperbolic cosine function, such as when resistance or strain builds up on a body increasingly as it is rotated (hysteresis).


## ASIN

Returns the angle (measured in radians) having the specified value of the trigonometric sine function.

**ASIN(value)**

Value is the sine value of the angle you want. Legal sine values are confined to real numbers from -1 to 1, inclusive.

The angle returned will be between -PI ()/2 and PI ()/2 radians. To convert this angle into degrees, multiply by PI ()/180.


## ASINH

Returns the angle (measured in radians) having the specified value of its hyperbolic sine function.

**ASINH(value)**

Value is the hyperbolic sine of some angle (measured in radians) that you want to find. As you might expect, the values of the hyperbolic sine function (see the SINH function) increase at a hyperbolic rate, but one consequence is that these ever larger changes in the hyperbolic sine will correspond to ever smaller changes in the angle. This relationship is intrinsic to many of the mathematical and engineering applications of the inverse hyperbolic sine function, such as when resistance or strain builds up on a body increasingly as it is rotated (hysteresis).


## ATAN

Calculates the normalized angle (measured in radians) which has the specified tangent function value.

**ATAN(value)**

Value is a number containing a tangent function value that you want to retrieve the angle of. This function returns an angle of between PI ()/2 and -PI ()/2. Although the tangent function is undefined for values of PI ()/2 and -PI ()/2, the return value of this function is rounded to these values if Value is +INF or -INF, respectively.

This function is sometimes referred to as the inverse tangent function or the arctangent.

The angle returned is the principal value, as there exist an uncountable number of alternative angles satisfying the requirement of having Value as their tangent function value, at regular intervals of +/- PI() to either side of this principal value.

If you require a result in degrees, multiply the arctangent by 180/PI ().


## ATAN2

Calculates the angle made with the x-axis on a Cartesian coordinate plane by the specified (x, y) coordinates.

**ATAN2(x_ordinate, y_abscissa)**

X_ordinate is a number representing the distance along the x-axis of a Cartesian point. It may also be thought of as the adjacent leg of a right triangle, where the right angle is made by dropping a perpendicular line from (x_ordinate, y_abscissa) to the point (x_ordinate, 0) on the x-axis.

Y_abscissa is a number representing the distance along the y-axis of a Cartesian point. It may also be thought of as the opposite leg of the right triangle constructed above.

This variation on the arctangent (or inverse tangent function) calculates for you the angle, theta, made with the x-axis when you extend a line segment from the origin at (0, 0) to your specified coordinates at (x_ordinate, y_abscissa). This line segment can also be seen to be the hypotenuse of a right triangle, or the radius of the circle on which the point, (x_ordinate, y_abscissa), sits on the edge. This function is another way of looking at the trigonometric tangent function value that is useful in many applications because it affords you a more convenient parameterization for some tasks, such as converting from Cartesian to Polar coordinate systems.

The return value of this function is within the range of PI ()/2 and -PI ()/2 measured in radians. If you need to convert this value into degrees, then multiply the result by 180/PI ().

**ATAN () TAN ()**


## ATANH

Calculates the hyperbolic tangent of a specified angle measured in radians.

**TANH(value)**

Value is an angle measured in radians for which you want to calculate the hyperbolic tangent. If your angle is measured in degrees, multiply it by PI ()/180 to convert into radians. The hyperbolic tangent has a range from -1 to 1.

## CEILING

Returns the smallest whole number greater than or equal to the given number

**CEILING(number)**

Number is the numeric value you want to round.

## COS

Calculates the trigonometric cosine of a specified angle (measured in radians).

**COS(value)**

Value is the angle measured in radians for which you want to take the cosine. If your argument must be in degrees, multiply it by PI ()/180 to convert it into radians.

The cosine is a sinusoidal function with a period of 2*PI () radians. Its value is always between 1 and -1. It behaves like the sine function, SIN (), with a phase shift (phi) of -PI ()/4 radians.

The cosine function value derives from the geometric ratio between the length of the adjacent (non-hypotenuse) leg to the hypotenuse of a right triangle, when the hypotenuse has a length of one. It is continuous because at intervals of PI () radians the length of the adjacent leg and the hypotenuse are equal.

Another way of looking at this function is to imagine the hypotenuse is the radius, r, of a unit circle centered on a Cartesian plane with x- and y- axes. At any point on the edge of the unit circle, the hypotenuse makes an angle, theta, with the x-axis. The cosine function value of the angle theta is the distance from the center of the circle to the point in the direction of the x-axis. Applied in this fashion, the COS () function can be used to convert between Cartesian and Polar coordinate systems.

Both interpretations are equivalent because if you drop a line from a point on the unit circle that intersects the x-axis at a right angle you form a right triangle.

These trigonometric concepts appear frequently in many engineering, architectural and scientific applications.

## COSH

Returns the angle (measured in radians) having the specified value of its hyperbolic cosine function.

**ACOSH(value)**

Value is the hyperbolic cosine of some angle (measured in radians) that you want to find. As you might expect, the values of the hyperbolic cosine function (see the COSH function) increase at a hyperbolic rate, but one consequence is that these ever larger changes in the hyperbolic cosine will correspond to ever smaller changes in the angle. This relationship is intrinsic to many of the mathematical and engineering applications of the inverse hyperbolic cosine function, such as when resistance or strain builds up on a body increasingly as it is rotated (hysteresis).

## EVEN

Rounds a positive number up and a negative number down to the nearest even integer.

**EVEN(Number)**

Number is the value to round.


## ODD

Rounds a positive number up and a negative number down to the nearest odd integer.

**ODD(Number)**

Number is the value to round.

## EXP

Calculates the mathematical constant, e, raised to the specified power.

**EXP(exponent)**

Exponent is the power to which the base, e, is raised. This gives the function it's characteristic "exponential" growth.

Euler's Number, e, is the value 2.718281828459..., and is also the base of the natural logarithm. You can represent the constant e within your formula by specifying EXP (1). The exponential function (and natural logarithm) have many applications in mathematics, engineering, and for modeling behavioral and statistical distributions commonly observed in nature and the social sciences.


## EXPON

"^" Exponentiation formula operator (3^2)

## FLOOR

Calculates the next lesser whole number for a specified numeric value.



**FLOOR(value)**

Value is a real numeric value to be rounded down to the next lesser whole number (also called an integer). FLOOR () behaves differently from the [INT ()]() function because when value is negative, the "next lesser whole number" will be a number having greater magnitude (i.e., it becomes more negative.)

## INT

Converts a real numeric value (which may have a fractional part) into a whole number.



**INT(value)**

Value is a real numeric value that you want to convert into a whole number. INT () is a more specialized version of the [TRUNC ()]() function because it always produces integer values (whereas the TRUNC () function allows you to specify a precision at which to truncate the numeric value.)

## LN

Calculates the natural logarithm of a specified numeric value.



**LN(value)**

Value is a real number to calculate the natural logarithm of. Value must be positive as the logarithm is undefined for negative values.

A natural logarithm is a special case of a logarithm having the base of Euler's Number, e (2.71828...). It is the inverse of the [EXP ()]() function.

Logarithms have many applications in mathematics, life and social sciences.


## LOG

Calculates a logarithm for a specified numeric value to the specified base.



**LOG (value, base)**

Value is a real number that you want to calculate the logarithm to base for. This number must be positive, as the logarithm is undefined for negative numbers.

Base is the base of the logarithm, which defaults to 10.

To calculate the natural logarithm (a logarithm to the base of Euler's Number, e) it is usually more convenient to call the [LN ()]() function.

## LOG10

Calculates the logarithm (base 10) of a specified numeric value.



**LOG10(value)**

Value is a real number to calculate the decimal logarithm of. Value must be positive as the logarithm is undefined for negative values.

To specify your own base for a logarithm, use the [LOG ()]() function. To calculate the natural logarithm, use the [LN ()]() function.

## MOD

Gets the remainder following integer division of two numbers.



**MOD (numerator, denominator)**

Numerator is the number being divided by denominator. When denominator can only be taken from numerator a certain whole number of types (the quotient), any leftover is the remainder.

Denominator is the number dividing the numerator. Any remainder will have the sign of the denominator. This number cannot be zero, otherwise the MOD () function returns a #DIV/0 error.

If you want to perform integer division on these two numbers, then use the [QUOTIENT ()]() function.


## PI

Returns the mathematical constant for the Greek letter, pi.



**PI()**

The mathematical constant pi represents the relationship between a circle's diameter and its circumference. It is also the constant relating the square of a circle's radius with the surface area of the circle. It has a great many applications in mathematics, geometry, the sciences, and engineering.

The constant pi is a non-terminating decimal number, although UnitCAD approximates it to 15 significant digits of precision (3.14159265358979).

A common use of the PI function in UnitCAD is to convert a measurement in radians which is the form in which trigonometric functions take their arguments, and the more conventional degrees of arc. This conversion can be accomplished by multiplying the radian measurement by PI ()/180. The following table describes some benchmarks for comparison between radians and degrees.

|Radians| Degrees|Turns of a wheel (common example)|
|:------|:-------|:--------------------------------|
|0|0|no turns|
|PI/4|45|one-eighth turn|
|PI/2|90|one-quarter turn|
|PI|180|one-half turn|
|2x PI|360|one complete turn|
|3x PI|540|one and one-half turn|


## POWER

Raises the specific number to a power.



**POWER (value, exponent)**

Value is a numeric value or reference to a numeric value which you want to raise to a power.

Exponent is a real number power to which value is to be raised. Imaginary exponents are not supported.

Common applications of the POWER () function occur when you need to multiply a number against itself multiple times. For example, it is common in many computer applications to create bit mask values by raising the value 2 to integer exponents, which produce a sequence such as (1, 2, 4, 8, 16, 32, 64, 128, ...)

The POWER () function additionally supports fractional exponents, and can be used to emulate other functions such as the quad root (raising to an exponent of 0.25, which is 1/4) or the inverse square (raising to an exponent of -2.0).


## PRODUCT

Multiplies a series of numbers to return their total product.



**PRODUCT (value1, value2, ..., valueN)**

Value1 is the first number (the multiplicand) in a series of numbers that you want to multiply.

Value2 is the second number (the first multiplier) in a series of numbers that you want to multiply.

ValueN is the last number (the last multiplier) in a series of numbers that you want to multiply.

This function offers a convenience when you need to multiply many numbers or expressions at one time.


## QUOTIENT

Performs integer division on two numbers disregarding any remainder.

**QUOTIENT(numerator, denominator)**

Numerator is a numeric value that will be divided by the denominator. It is sometimes called the dividend.

Denominator is the numeric value that divides the numerator. It is sometimes called the divisor. It cannot be zero or a #DIV/0 error value will be returned.

When either the numerator or the denominator is not a number, the QUOTIENT() function returns an error value (#VALUE!).

If you need the remainder from an integer division, use the MOD() function.


## RAND

Generates a pseudorandom number from zero up to (but not including) one.

**RAND ()**

The RAND () function will generate another pseudorandom number each time it is evaluated. It returns a fractional number on a unit basis, therefore you can use RAND () to produce numbers between 0 and C by multiplying the RAND () result by C. It follows that to produce a pseudorandom number between A and B you could translate the result by A like this:

**RAND () * ([B] - [A]) + [A]**

The number generation of the RAND () function derives from the system clock, and therefore may not be entirely random. It should not be used for applications requiring cryptographically-strong randomness or uniform probability distributions.


## ROUND

Rounds the fractional portion of a numeric value up or down to produce an integer.



**ROUND (value, number_of_digits)**

Value is a numeric value or reference to a numeric value that you want to round up or down.

Number_of_digits specifies the precision at which rounding should occur. This will be the place value which UnitCAD examines to round up or down. By default, rounding occurs zero places right of the decimal point produces an integer.


## SQRT

Calculates the square root of a number.



**SQRT(value)**

Value is the numeric value or reference to a numeric value which you are calculating the square root of. Only real roots are supported, therefore if value is negative (which would produce an imaginary root) the SQRT () function will return an error value (#NUM!).

The square root is the number whose product, when the number is multiplied against itself (squared), is value. Note that it is possible to multiply two negative square roots to produce the same positive value. By convention, the SQRT () function only returns the positive root.


## SIN

Calculates the trigonometric sine of a specified angle (measured in radians).



**SIN(value)**

Value is the angle measured in radians for which you want to take the cosine. If your argument must be in degrees, multiply it by PI ()/180 to convert it into radians.

The sine is a sinusoidal function with a period of 2*PI () radians. Its value is always between 1 and -1.

The sine function value derives from the geometric ratio between the length of a right triangle's hypotenuse and the length of the opposite leg, when the hypotenuse has a length of one. It is a continuous function because at intervals of PI () radians the length of the opposite leg and the hypotenuse are equal.

Another way of looking at this function is to imagine the hypotenuse is the radius, r, of a unit circle centered on a Cartesian plane with x- and y- axes. At any point on the edge of the unit circle, the hypotenuse makes an angle, theta, with the x-axis. The sine function value of the angle theta is the distance from the center of the circle to the point in the direction of the y-axis. Applied in this fashion, the SIN () function can be used to convert between Cartesian and Polar coordinate systems.

Both interpretations are equivalent because if you drop a line from a point on the unit circle that intersects the y-axis at a right angle you form a right triangle.

These trigonometric concepts appear frequently in many engineering, architectural and scientific applications.


## SINH

Calculates the hyperbolic sine of a specified angle measured in radians.



**SINH(value)**

Value is an angle measured in radians for which you want to calculate the hyperbolic sine. If your angle is measured in degrees, multiply it by PI ()/180 to convert into radians.

Many applications in mathematics and physics, for example determining the gravitational potential of a cylinder, make use of the hyperbolic sine function's characteristics.

## SUM

Adds a series of numbers to obtain a total amount.



**SUM (value1, value2,...)**

Value1, value2, ... are references for which you want to find the total value. Text representations of numbers and literal numeric constants that you specify in the list of arguments will be included in the sum. If value is a column or vector reference then the sum will be taken of all cells or values contained by the reference. Any error values in the argument list, or text that is not convertible to a numeric value, will produce an error.

## TAN

Calculates the trigonometric tangent of a specified angle (measured in radians).



**TAN(value)**

Value is the angle measured in radians for which you want to take the tangent. If your argument must be in degrees, multiply it by PI ()/180 to convert it into radians.

The tangent can have a value from -INF to +INF, however it is undefined at intervals of every PI ()/2 radians +/- PI () radians.

The tangent function value derives from a well-known geometric ratio between the length of the opposite and the adjacent (non-hypotenuse) leg of a right triangle. All 3 angles inside of any triangle must add up to exactly PI () radians, and in a right triangle the angle opposite the hypotenuse must be PI ()/2 radians. Given these facts, it is not possible for either of the other two angles within the triangle to reach PI ()/2 radians themselves. If you choose an angle (other than the triangle's right angle) which approaches PI ()/2 radians, then the remaining angle must approach 0 radians. The tangent function value tells you in these circumstances how the leg of the right triangle opposite your angle approaches infinite length. These calculations have important applications in architecture and engineering.


## TANH

Calculates the hyperbolic tangent of a specified angle measured in radians.



**TANH(value)**

Value is an angle measured in radians for which you want to calculate the hyperbolic tangent. If your angle is measured in degrees, multiply it by PI ()/180 to convert into radians. The hyperbolic tangent has a range from -1 to 1.


## TRUNC

Truncates the fractional portion of a numeric value to produce an integer.



**TRUNC (value, number_of_digits)**

Value is a numeric value or reference to a numeric value that you want to truncate.

Number_of_digits specifies the precision at which truncation should occur. By default, truncation occurs zero places right of the decimal point which will produce an integer.

Truncation always discards the fractional value, causing the Value to move closer to zero (whether it was positive or negative before the truncation). It differs from the ROUND () function in that the value always changes to a lesser value.


## COMBIN

Returns the number of possible combinations given a set of items and a number of chosen items from that set.

**Combin(number, numberChosen)**

Number is the number of items.

NumberChosen is the number of items chosen in each combination.


## DEGREES

Converts radians to degrees.


**DEGREES(radians)**

Radians is a value in radians which will be converted to degrees.


## FACT

Returns the factorial of a number.

**FACT(number)**

Number is a positive number for which the factorial will be calculated.



## FACTDOUBLE

Returns the double factorial of a number.


**FACTDOUBLE(number)**

Number is a positive number for which the double factorial will be calculated.



## GCD

Returns the greatest common divisor of integer values.


**GCD (number1, [number2, number3, ..., numberN])**

Number1, Number2, ..., NumberN is any number of integers.



## LCM

Returns the least common multiple of integer values.

**LCM (number1, [number2, number3, ..., numberN])**

Number1, Number2, ..., NumberN is any number of integers.


## MROUND

Rounds a number to the nearest multiple of another number.

**MRound(number, multiple)**

Number is a number to be rounded.

Multiple is a number indicating the multiple to which to round.


## MULTINOMINAL

Returns the multinomial of a set of numbers.

**MULTINOMIAL (number1, [number2, number3, ..., numberN])**

Number1, Number2, ..., NumberN is any number of numbers.



## RADIANS

Converts degrees to radians.

**RADIANS(degrees**

Degrees is a value in degrees which will be converted to radians.


## RANDBETWEEN

Generates a pseudorandom integer between two specified numbers.

**RANDBETWEEN (bottom, top)**

Bottom is the minumum value that will be returned.

Top is the maximum value that will be returned.


## ROMAN

Converts a number into a roman number as a string.


**ROMAN (number, form)**

Number is the number to convert to roman numerals.

Form is a number or boolean value indicating whether to use classic roman numerals or a more concise version.

0 = (Default) Classic. (499 = "CDXCIX") 1 = More concise. (499 = "LDVLIV") 2 = More concise. (499 = "XDIX") 3 = More concise. (499 = "VDIV") 4 = Simplified. (499 = "ID") TRUE = Classic. FALSE = Simplified.



## ROUNDDOWN

Rounds a number to down to the specified number of digits.


**ROUNDDOWN (number, digits)**

Number is a number to be rounded down.

Digits indicates the number of decimal places to round to. Positive numbers indicate places after the decimal point, negative numbers indicate places before the decimal point.


## ROUNDUP

Rounds a number to up to the specified number of digits.


**ROUNDUP (number, digits)**

Number is a number to be rounded up.

Digits indicates the number of decimal places to round to. Positive numbers indicate places after the decimal point, negative numbers indicate places before the decimal point.



## SERIESSUM

Returns the sum of a power series.


**SERIESSUM (inputValue, initialPower, step, coefficient1 [, coefficient2, coefficient3, ..., coefficientN])**

InputValue is the input value to the power series.

InitialPower is the initial power to which X will be raised.

Step is the step which will be used to increase N for each term in the series.

Coefficient1, Coefficient2, ..., CoefficientN is a set of coefficients by which each successive power of X is multiplied.


## SIGN

Returns the sign of a number. (-1, 0, or 1)

**SIGN(number)**

The number whose sign wil be returned.


## SQRTPI

Returns the square root of the specified number times Pi.

**SQRTPI(number)**

The number which will be multiplied by Pi.
