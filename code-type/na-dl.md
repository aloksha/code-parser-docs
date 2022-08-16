---
layout: default-layout
title: Supported code types - Dynamsoft Code Parser SDK 
description: This is the supported code types page of Dynamsoft Label Recoginizer SDK.
keywords: code types
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# North American Driver License

Following table shows what `ParseField`s could be contained in a North American driver license's parse result:

| FieldName | Definition | Element ID |
|---|---|---|
| version | AAMVA Version Number | - |
| ISOIIN | Issuer Identification Number | - |
| fullName | full name of the license holder | DAA |
| jurisdictionVehicleCode | Jurisdiction-specific vehicle class / group code, designating the type of vehicle the cardholder has privilege to drive. | DAR/DCA |
| jurisdictionRestrictionCode | Jurisdiction-specific codes that represent restrictions to driving privileges (such as airbrakes, automatic transmission, daylight only, etc.). | DAS/DCB |
| jurisdictionEndorsementsCode | Jurisdiction-specific codes that represent additional privileges granted to the cardholder beyond the vehicle class (such as transportation of passengers, hazardous materials, operation of motorcycles, etc.). | DAT/DCD |
| expirationDate | Date on which the driving and identification privileges granted by the document are no longer valid. (MMDDCCYY for U.S., CCYYMMDD for Canada) | DBA |
| lastName | Family name of the cardholder. (Family name is sometimes also called “last name” or “surname.”) | DAB/DCS |
