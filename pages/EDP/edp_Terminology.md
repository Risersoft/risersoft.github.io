---
title: Terminology
keywords: Terminology
sidebar: edp_sidebar
permalink: easy-data-porter/terminology.html
folder: EDP
hide_sidebar: false
comments: false
---

# Terminology

 

•**Source Connections (*.edpsc.xml)**

These are source connections which provide access to source data. Various source connectors are included with Easy Data Porter such as SQL Server, Access, Oracle, MySQL, ODBC etc.

Source connections can also be saved by user to point to a specific database / file and reused later.

 

•**Target Connections (*.edptc.xml)**

These are target connections which provide the data source to which transformed data is to be written. Currently Easy Data Porter provides Text Delimited and Text Fixed Width target connectors.

Target connections can also be saved by user to point to a specific file and reused later.

 

•**Source and Target Schema (*.edpsa.xml)**

Schema provides Easy Data Porter with structure of information. Source Schema definition depends on whether the source connection provides schema information or not. Target Schema needs to be provided in all cases.

 

•**Maps (*.edpmap.xml)**

Maps provide Easy Data Porter with information on how to transform the source data into target data. You can define the Map Expression for each target field in an Excel-like formula language with special functions to provide access to source data target fields.

 

Map files also contain complete connection and schema information. The Schema and connection files can be saved separately and imported later into a map file.

 

