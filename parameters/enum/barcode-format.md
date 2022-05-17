---
layout: default-layout
title: Dynamsoft Core Enumerations - BarcodeFormat
description: This article shows the BarcodeFormat enumeration of Dynamsoft Core.
keywords: enumerations, BarcodeFormat
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---


# BarcodeFormat

Describes the barcode types in BarcodeFormat group 1. All the formats can be combined, such as BF_CODE_39 | BF_CODE_128. 
>Note: The barcode format our library supported is composed of [BarcodeFormat group 1](#barcodeformat) and [BarcodeFormat group 2](barcode-format-2.md), so you need to specify the barcode format in group 1 and group 2 individually.

## Declarations
   
| Language | Declaration |
| -------- | ----------- |
| C / C++ | `enum BarcodeFormat` |
| .Net | `enum Dynamsoft.Core.EnumBarcodeFormat ` |
| Android | `class com.dynamsoft.core.EnumBarcodeFormat` |
| ObjC / Swift | `enum EnumBarcodeFormat` |
| Java | `class com.dynamsoft.core.EnumBarcodeFormat` |


## Members
   
| Member (except ObjC/Swift) | Member (ObjC/Swift) | Value | Description |
| -------------------------- | ------------------- | ----- | ----------- |
| BF_ALL | EnumBarcodeFormatALL | -31457281 | All supported formats in [BarcodeFormat group 1](#barcodeformat). |
| BF_ONED | EnumBarcodeFormatONED  | 0x001007FF | Combined value of BF_CODABAR, BF_CODE_128, BF_CODE_39, BF_CODE_39_Extended, BF_CODE_93, BF_EAN_13, BF_EAN_8, INDUSTRIAL_25, BF_ITF, BF_UPC_A, BF_UPC_E, BF_MSI_CODE. |
| BF_GS1_DATABAR | EnumBarcodeFormatGS1DATABAR | 0x0003F800 | Combined value of BF_GS1_DATABAR_OMNIDIRECTIONAL, BF_GS1_DATABAR_TRUNCATED, BF_GS1_DATABAR_STACKED, BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL, BF_GS1_DATABAR_EXPANDED, BF_GS1_DATABAR_EXPANDED_STACKED, BF_GS1_DATABAR_LIMITED. | 
| BF_NULL | EnumBarcodeFormatNULL | 0x00 | No barcode format in [BarcodeFormat group 1](#barcodeformat). |
| BF_CODE_39 | EnumBarcodeFormatCODE39 | 0x01 | Code 39 |
| BF_CODE_128 | EnumBarcodeFormatCODE128 | 0x02 | Code 128 |
| BF_CODE_93 | EnumBarcodeFormatCODE93 | 0x04 | Code 93 |
| BF_CODABAR | EnumBarcodeFormatCODABAR | 0x08 | Codabar |
| BF_ITF  | EnumBarcodeFormatITF | 0x10 | ITF |
| BF_EAN_13 | EnumBarcodeFormatEAN13 | 0x20 | EAN-13 |
| BF_EAN_8 | EnumBarcodeFormatEAN8 | 0x40 | EAN-8 |
| BF_UPC_A | EnumBarcodeFormatUPCA | 0x80 | UPC-A |
| BF_UPC_E | EnumBarcodeFormatUPCE | 0x100 | UPC-E |
| BF_INDUSTRIAL_25 | EnumBarcodeFormatINDUSTRIAL | 0x200 | Industrial 2 of 5 |
| BF_MSI_CODE | EnumBarcodeFormatMSICODE | 0x100000 | MSI Code |
| BF_CODE_39_EXTENDED | EnumBarcodeFormatCODE39EXTENDED | 0x400 | Code 39 Extended |
| BF_GS1_DATABAR_OMNIDIRECTIONAL | EnumBarcodeFormatGS1DATABAROMNIDIRECTIONAL | 0x800 | GS1 Databar Omnidirectional |
| BF_GS1_DATABAR_TRUNCATED | EnumBarcodeFormatGS1DATABARTRUNCATED | 0x1000 | GS1 Databar Truncated |
| BF_GS1_DATABAR_STACKED | EnumBarcodeFormatGS1DATABARSTACKED | 0x2000 | GS1 Databar Stacked |
| BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL | EnumBarcodeFormatGS1DATABARSTACKEDOMNIDIRECTIONAL | 0x4000 | GS1 Databar Stacked Omnidirectional |
| BF_GS1_DATABAR_EXPANDED | EnumBarcodeFormatGS1DATABAREXPANDED | 0x8000 | GS1 Databar Expanded |
| BF_GS1_DATABAR_EXPANDED_STACKED | EnumBarcodeFormatGS1DATABAREXPANDEDSTACKED | 0x10000 | GS1 Databar Expaned Stacked |
| BF_GS1_DATABAR_LIMITED | EnumBarcodeFormatGS1DATABARLIMITED | 0x20000 | GS1 Databar Limited |
| BF_PATCHCODE | EnumBarcodeFormatPATCHCODE | 0x00040000 | Patch code |
| BF_MICRO_PDF417 | EnumBarcodeFormatMICROPDF417 | 0x00080000 | Micro PDF417 |
| BF_PDF417 | EnumBarcodeFormatPDF417 | 0x02000000 | PDF417 |
| BF_QR_CODE | EnumBarcodeFormatQRCODE | 0x04000000 | QRCode |
| BF_DATAMATRIX | EnumBarcodeFormatDATAMATRIX | 0x08000000 | DataMatrix |
| BF_AZTEC | EnumBarcodeFormatAZTEC | 0x10000000 | AZTEC |
| BF_MAXICODE | EnumBarcodeFormatMAXICODE | 0x20000000 | MAXICODE |
| BF_MICRO_QR | EnumBarcodeFormatMICROQR | 0x40000000 | Micro QR Code |
| BF_GS1_COMPOSITE | EnumBarcodeFormatGS1COMPOSITE | -2147483648 | GS1 Composite Code |
