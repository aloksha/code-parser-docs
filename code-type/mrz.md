---
layout: default-layout
title: Supported code types - Dynamsoft Code Parser SDK 
description: This is the supported code types page of Dynamsoft Label Recoginizer SDK.
keywords: code types
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# MRZ

All versions of Machine Readable Travel Documents (MRTD) specified by the International Civil Aviation Organization (ICAO) are supported. Following table shows what fields could be contained in a MRZ's parse result:

| FieldName | Definition |
|---|---|
| documentCode | Two characters, shall be used to designate the particular type of document. |
| issuingState | The three-letter code specified in [Doc 9303-3](https://www.icao.int/publications/Documents/9303_p3_cons_en.pdf) shall be used. |
| documentNumber | As given by the issuing State or organization, to uniquely identify the document from all other MROTDs issued by the State or organization. |
| checkDigitForDocumentNumber | The method of calculating check digits is given in Doc 9303-3. |
| passportNumber | As given by the issuing State or organization to uniquely identify the passport. |
| checkDigitForPassportNumber | The method of calculating check digits is given in Doc 9303-3. |
| optionalData1 | For optional use. |
| personalNumber | Any special characters, including spaces in the personal identification number given to the holder by the issuing State or organization. |
| checkDigitForPersonalNumber | The method of calculating check digits is given in Doc 9303-3. |
| dateOfBirth | Date of birth. |
| checkDigitForBirthDate | The method of calculating check digits is given in Doc 9303-3. |
| sex | F = female; M = male; < = unspecified. |
| dateOfExpiry | Date of expiry. |
| checkDigitForExpiryDate | The method of calculating check digits is given in Doc 9303-3. |
| nationality | Same as issuingState. |
| optionalData2 | For use of the issuing State or organization. |
| compositeCheckDigit | Composite check digit to verify the data element of the upper and middle machine readable lines.  |
| lastName | LastName of the document holder. |
| givenName | GivenName of the document holder. |
