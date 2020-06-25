---
title: List Functions
keywords: List Functions
sidebar: forlang_sidebar
permalink: formula-language/list-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---

# List Functions


## ELEMCOUNT

Returns number of elements in a list.

**ELEMCOUNT(List)**

List is a parameter of type list.


## NTH

Returns the nth element from the list.

**NTH(list,index)**

List is a parameter of type list.

Index is the index of the element to return. The returned element can be of any data type.


## KEYVALUE

Returns the value of a specified key in the list, considering the list is made of key-value pairs.

**KEYVALUE(List,Key)**

List is a parameter of type list.

Key is the key for which value is required. The returned value can be of any data type.


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



## ListHasValue

Returns True/False depending on whether the list contains the specified value.

**ListHasValue(List,Value)**

List is a parameter of type list.

Value is the value of find and can be of any literal type.
