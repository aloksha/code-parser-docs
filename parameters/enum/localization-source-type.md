---
layout: default-layout
title: Dynamsoft Code Parser Enumerations - LocalizationSourceType
description: This article shows the LocalizationSourceType enumeration of Dynamsoft Code Parser.
keywords: enumerations, LocalizationSourceType
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# LocalizationSourceType
Describes the source type used to localize the reference region(s).

## Declarations
   
| Language | Declaration |
| -------- | ----------- |
| C / C++ | `enum LocalizationSourceType` |
| .Net | `enum Dynamsoft.DLR.EnumLocalizationSourceType` |
| Android | `class com.dynamsoft.dlr.EnumLocalizationSourceType` |
| ObjC / Swift | `enum EnumLocalizationSourceType` |
| Java | `class com.dynamsoft.dlr.EnumLocalizationSourceType` |


## Members
   
| Member (except ObjC/Swift) | Member (ObjC/Swift) | Value | Description |
| -------------------------- | ------------------- | ----- | ----------- |
| LST_MANUAL_SPECIFICATION | EnumLocalizationSourceTypeManualSpecification | 0x01 | Define the reference region using the manually specified location. |
| LST_PREDETECTED_REGION | EnumLocalizationSourceTypePredetectedRegion | 0x02 | Define the reference region using the result(s) of region predetection process. |
| LST_BARCODE | EnumLocalizationSourceTypeBarcode | 0x04 | Define the reference region using the barcode info. |
