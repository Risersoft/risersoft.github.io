---
title: Engineering Functions
keywords: Engineering Functions
sidebar: forlang_sidebar
permalink: formula-language/engineering-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---

# Engineering Functions

## BIN2DEC

Returns the decimal value of a string representation of a number in a binary system.

**Bin2Dec(number)**

Number is a string representing a binary number.

## BIN2HEX

Converts a string representing a binary number to a string representing the same number in the hexadecimal number system.

**Bin2Hex (number, places)**

Number is the value to be converted.

Places is the number of characters to use in representing the value. If places are not specified, the mimumum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.

## BIN2OCT

Converts a string representing a binary number to a string representing the same number in the octal number system.

**Bin2Oct (number, places)**

Number is the value to be converted.

Places is the number of characters to use in representing the value. If places are not specified, the mimumum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.

## COMPLEX

Returns a complex number represented as a string in the format "x + yi" or "x + yj" by comining a real and imaginary number.

**COMPLEX (realNumber, imaginaryNumber, [suffix])**

RealNumber is the real coefficient of the complex number.

ImaginaryNumber is the imaginary coefficient of the number.

Suffix specifies the suffix to use. The acceptable values are "i" or "j". If omitted, "i" is used. Note that the suffix is case-sensitive; upper case "I" and "J" are not allowed and will result in a #VALUE error.

## CONVERT

Converts a value from one system of measurement to another. For example, meters to inches or hours to seconds.

**CONVERT (number, fromUnit, toUnit)**

Number is the value to convert.

FromUnit is the unit in which the number is given.

ToUnit is the units to convert to.

Weight and mass units: "g" = gram "sg" = slug "lbm" = pound mass (avoirdupois) "u" = U (atomic mass unit) "ozm" = Ounce mass (avoirdupois)

Distance units: "m" = Meter "mi" = Statute mile "Nmi" = Nautical mile "in" = Inch "ft" = Foot "yd" = Yard "ang" = Angstrom "Pica" = Pica (1/72 in.)

Time units: "yr" = Year "day" = Day "hr" = Hour "mn" = Minute "sec" = Second

Pressure units "Pa" (or "p") = Pascal "atm" (or "at") = Atmosphere "mmHg" = mm of Mercury

Force units "N" = Newton "dyn" (or "dy") = Dyne "lbf" = Pound force

Energy units: "J" = Joule "e" = Erg "c" = Thermodynamic calorie "cal" = IT calorie "eV" (or "ev") = Electron volt "HPh" (or "hh") = Horsepower-hour "Wh" (or "wh") = Watt-hour "flb" = Foot-pound "BTU" (or "btu") = BTU

Power units: "HP" (or "h") = Horsepower "W" (or "w") = Watt

Magentism units: "T" = Tesla "ga" = Gauss
Temperature units: "C" (or "cel") = Degree Celsius "F" (or "fah") = Degree Fahrenheit "K" (or "kel") = Kelvin

Liquid measure units: "tsp" = Teaspoon "tbs" = Tablespoon "oz" = Fluid ounce "cup" = Cup "pt" (or "us_pt") = U.S. pint "uk_pt" = U.K. pint "qt" = Quart "gal" = Gallon "l" (or "lt") = Liter

Any metric ToUnit or FromUnit may be prefixed with one of the following: exa ("E") = 1E+18 peta ("P") = 1E+15 tera ("T") = 1E+12 giga ("G") = 1E+09 mega ("M") = 1E+06 kilo ("k") = 1E+03 hecto ("h") = 1E+02 dekao ("e") = 1E+01 deci ("d") = 1E-01 centi ("c") = 1E-02 milli ("m") = 1E-03 micro ("u") = 1E-06 nano ("n") = 1E-09 pico ("p") = 1E-12 femto ("f") = 1E-15 atto ("a") = 1E-18


## DEC2BIN

Returns a string representing the specified decimal value as a binary number.

**Dec2Bin (number, places)**

Number is the decimal value to be converted.

Places is the number of characters to use in representing the value. If places are not specified, the minimum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.


## DEC2HEX

Returns a string representing the specified decimal value as a hexadecimal number.

**Dec2Hex (number, places)**

Number is the decimal value to be converted.

Places is the number of characters to use in representing the value. If places is not specified, the minimum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.

## DEC2OCT

Returns a string representing the specified decimal value as an octal number.

**Dec2Oct (number, places)**

Number is the decimal value to be converted.

Places is the number of characters to use in representing the value. If places are not specified, the minimum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.

## DELTA

Compares two numbers and returns 1 if they are equal or 0 if they are not.

**DELTA (number1, [number2])**

Number1 is a number.

Number2 is a number. If Number2 is not specified, Number1 will be compared to 0.

## GESTEP

Compares two numbers and returns 1 the first number is greater than or equal to the second or returns 0 if not.

**GESTEP (number, [step])**

Number is a number.

Step is a number. If step is not specified, Number will be compared to 0.

## HEX2BIN

Converts a string representing a hexadecimal number to a string representing the same number in the binary number system.

**Hex2Bin (number, places)**

Number is the value to be converted.

Places is the number of characters to use in representing the value. If places are not specified, the minimum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.


## HEX2DEC

Returns the decimal value of a string representation of a number in a hexadecimal system.

**Hex2Dec(number)**

Number is a string representing a hexadecimal number.

## HEX2OCT

Converts a string representing a hexadecimal number to a string representing the same number in the octal number system.

**Hex2Oct (number, places)**

Number is the value to be converted.

Places is the number of characters to use in representing the value. If places are not specified, the minimum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.

## IMABS

Returns the absolute value of a complex number.

**IMABS(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMAGINARY

Returns the imaginary coefficient of a complex number.

**IMAGINARY(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMARGUMENT

Returns the argument theta, and angle expressed in radians.

**IMARGUMENT(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMCONJUGATE

Returns the conjugate of a complex number.

**IMCONJUGATE(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMCOS

Returns the cosine of a complex number.

**IMCOS(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMDIV

Returns the quotient of two complex numbers.

**IMDIV (dividend, divisor)**

Dividend is a complex number in the format: "x + yi" or "x + yj".

Divisor is a complex number in the format: "x + yi" or "x + yj".

## IMEXP

Returns the exponential of a complex number.

**IMEXP(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMLN

Returns the natural logarithm of a complex number.

**IMLN(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMLOG10

Returns the base-10 logarithm of a complex number.

**IMLOG10(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMLOG2

Returns the base-2 logarithm of a complex number.

**IMLOG2(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMPOWER

Returns the complex number raised to the specified power.

**IMPOWER (complexNumber, power)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

Power is the power to which ComplexNumber will be raised.

## IMPRODUCT

Returns the product of 1 to n complex numbers.



**IMPRODUCT (complexNumber1 [, complexNumber2, complexNumber3, ..., complexNumberN])**

ComplexNumber1, ComplexNumber2, ..., ComplexNumberN is any number of complex numbers in the format: "x + yi" or "x + yj" which will be multiplied together.


## IMREAL

Returns the real coefficient of a complex number.



**IMREAL(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMSIN

Returns the sine of a complex number.

**IMSIN(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMSQRT

Returns the square root of a complex number.

**IMSQRT(complexNumber)**

ComplexNumber is a complex number in the format: "x + yi" or "x + yj".

## IMSUB

Returns the difference between two complex numbers.

**IMSUB (complexNumber1, complexNumber2)**

ComplexNumber1 is a complex number in the format: "x + yi" or "x + yj" from which ComplexNumber2 will be subtracted.

ComplexNumber2 is a complex number in the format: "x + yi" or "x + yj" which will be subtracted from ComplexNumber1.

## IMSUM

Returns the sum of 1 to n complex numbers.

**IMSUM (complexNumber1 [, complexNumber2, complexNumber3, ..., complexNumberN])**

ComplexNumber1, ComplexNumber2, ..., ComplexNumberN is any number of complex numbers in the format: "x + yi" or "x + yj" which will be added together.

## OCT2BIN

Converts a string representing an octal number to a string representing the same number in the binary number system.

**Oct2Bin (number, places)**

Number is the value to be converted.

Places is the number of characters to use in representing the value. If places are not specified, the minimum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.

## OCT2DEC

Returns the decimal value of a string representation of a number in an octal system.

**Oct2Dec(number)**

Number is a string representing an octal number.

## OCT2HEX

Converts a string representing an octal number to a string representing the same number in the hexadecimal number system.

**Oct2Hex (number, places)**

Number is the value to be converted.

Places is the number of characters to use in representing the value. If places are not specified, the minimum number of characters necessary to represent the value will be used. Places allows you to specify leading zeros.
