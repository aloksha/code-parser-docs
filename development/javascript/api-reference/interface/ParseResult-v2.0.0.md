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

* resultInfoType: *number &#124; [EnumResultInfoType](../enum/EnumResultInfoType-v2.0.0.md)*

  > The parsed result type.

* resultInfo: *Array<ParseField>*

  > The parsed result in Array<[ParseField](../interface/ParseField-v2.0.0.md)>.

* jsonStrResult: *string*

  > The parsed result in json string format.

* getValue(fieldName: string): string;

  > The method to get the value according to a field name.