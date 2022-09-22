---
layout: default-layout
title: Supported code types - Dynamsoft Code Parser SDK 
description: This is the supported code types page of Dynamsoft Label Recoginizer SDK.
keywords: code types
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# VIN

All standards of the Vehicle Identification Number (VIN) specified by the International Organization for Standardization (ISO) in 1979 and 1980: ISO 3779 and ISO 3780 are supported. 

Following tables show what fields could be contained in a VIN code's parsed result:

| FieldName | Definition | ChildField | Applied In |
|---|---|---|---|
| WMI | World Manufacturer Identifier. | region | all |
| region | English name of the region. | - | all |
| VDS | Vehicle Descriptor Section. Each manufacturer has a unique system for using this field. | - | all |
| checkDigit | A check-digit used to validate the VIN. | - | North America and China |
| VIS | Vehicle Identifier Section. Used by the manufacturer to identify the individual vehicle in question. | modelYear, plantCode, WMI-suffix, serialNumber | all |
| modelYear | Building or model year of a vehicle. Its parsed result is always an array because it is represented by one digit in VIN code and is only unique within a period of 30 years. | - | North America and China |
| plantCode | Manufacturer plant (assembly plant). | - | North America and China |
| WMI-suffix | A manufacturer who builds fewer than 1,000 vehicles per year uses a 9 as the third digit, and the 12th, 13th and 14th position of the VIN for a second part of the identification. | - | North America and China |
| serialNumber | Serial number of the car. | - | North America and China |
