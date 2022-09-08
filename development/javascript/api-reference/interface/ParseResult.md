---
layout: default-layout
title: ParseResult - Dynamsoft Code Parser JavaScript Interface
description: This page shows the ParseResult interface of Dynamsoft Code Parser for JavaScript.
keywords: ParseResult, javascript, interface
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: ParseResult
---

# ParseResult

`interface` ParseResult

* codeType: *number &#124; [EnumCodeType](../enum/EnumCodeType.md)*

  > The value of parsed result's type.

* codeTypeString: *string*

  > The name of parsed result's type.

* specificationName: *string*

  > The specification's name which the parsing based on.

* resultInfo: *any*

  > The parsed result in json object.

* getFieldValueByName(fieldName: string): *string*;

  > The method to get the value according to a field name.
