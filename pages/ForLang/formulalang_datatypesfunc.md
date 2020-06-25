---
title: Data types
keywords: Data types
sidebar: forlang_sidebar
permalink: formula-language/data-types.html
folder: Forlang
hide_sidebar: false
comments: false
---



# Data types



## String

A **String** literal is a sequence of Unicode characters enclosed within ASCII double-quote characters. A string literal is of the **String** type, and contains zero or more Unicode characters.

**Insert a new line into a string**

There are two ways to insert a new line into a string: the newline() function, and directly entering the newline in the string.

```
‘Insert a new line using newline() function

"Load = " & load1 & "kg." & newline() & "Load is out of range."

‘Insert a new line directly

"Load = " & load2 & "kg.

Load is out of range.")

```

The first example is the preferred style.


## Number

A **Number** literal is an integer literal followed by a decimal point. The optional decimal point is represented by the ASCII period character. A **Number** literal is of type Number.


```
200.0

0.02
```


## Boolean

**Boolean** literals **True** and **False** map to the true and false state, respectively.


## Point

A **Point** is a representation of a location in space. It contains X, Y, and Z coordinates.

## List

A **List** is a collection of elements of any data type. **List** elements can be of any valid **UnitCAD** data type, including other lists. Each member of a list can be of a different data type. Empty lists are allowed.



The following example shows a list that contains five elements of type **Number**:

```
List (17, 5, 64, 2, 88)

```

A list is persisted as a JSON string and contains value and datatype information is required. In formulas, typically the list function is used to instantiate the list.

 The following example shows a list whose elements are of various data types. This list contains both literals and other list objects.

```
List (12, 32.4, "TEST", List ("Item No.", 10272004), List ("Description", "Sprocket"),0)

```


## Vector

A **Vector** represents a direction and a magnitude. It has X, Y, Z components and optionally a W component for Homogeneous Coordinates.


## Plane

A **Plane** represents a plane in 3d Space and specified by a vector and distance from origin.
