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

* resultInfoType: *number &#124; [EnumResultInfoType](../enum/EnumResultInfoType.md)*

  > The parsed result type.

* resultInfo: *Array<[ParseField](ParseField.md)>*

  > The parsed result in Array<[ParseField](ParseField.md)>.

* jsonResult: *any*

  > The parsed result in json object.

* getFieldValueByName(fieldName: string): *string*;

  > The method to get the value according to a field name.
