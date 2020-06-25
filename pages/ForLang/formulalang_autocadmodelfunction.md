---
title: AutoCAD Model Functions
keywords: AutoCAD Model Functions
sidebar: forlang_sidebar
permalink: formula-language/autocad-model-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---

# AutoCAD Model Functions

All model functions which return a point generally translate the co-ordinate in the context of the current component definition.


## CENPOINT

Returns the center point of a circular entity.

**CENPOINT(entity)**

Entity is a string representing a circular entity in the context of current component or its children.



## QUADPOINT

Returns the quad point of a circular entity.

**QUADPOINT(entity,index)**

Entity is a string representing an entity in the context of current component or its children.

Index is the index of the point to return.


## MIDPOINT

Returns the midpoint of a line entity.

**MIDPOINT(entity)**

Entity is a string representing an entity in the context of current component or its children.



## ENDPOINT

Returns the end point of a line entity.

**ENDPOINT(entity,index)**
Entity is a string representing a line entity in the context of current component or its children.

Index is the index of the point to return, 0 returns start point and 1 returns end point


## INTERPOINT

Returns the intersection point of two entities.

**INTERPOINT (entity1, entity2, index)**

Entity1 and Entity2 are strings representing a geometric entity in the context of current component or its children.

Index is the index of the point to return. 0 returns the first intersection point, 1 returns the second if there are more than 1 intersection points.


## BBC

Returns the bounding box co-ordinates of an entity.

**BBC (entity, datakey)**
Entity is a string representing an entity in the context of current component or its children.

Datakey is a string which determines which point of the bounding box to return – of the form “pxyz” where x, y,  z can be 0 or 1 to denote whether to output startpoint or endpoint in that axis.

Hence, Can be following values:

"p000”, "p001", "p010", "p011", "p100", “p101", "p110", "p111"
