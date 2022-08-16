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
| version | AAMVA Version Number. | - |
| ISOIIN | Issuer Identification Number. | - |
| fullName | full name of the license holder. | DAA |
| jurisdictionVehicleCode | Jurisdiction-specific vehicle class / group code, designating the type of vehicle the cardholder has privilege to drive. | DAR/DCA |
| jurisdictionRestrictionCode | Jurisdiction-specific codes that represent restrictions to driving privileges (such as airbrakes, automatic transmission, daylight only, etc.). | DAS/DCB |
| jurisdictionEndorsementsCode | Jurisdiction-specific codes that represent additional privileges granted to the cardholder beyond the vehicle class (such as transportation of passengers, hazardous materials, operation of motorcycles, etc.). | DAT/DCD |
| expirationDate | Date on which the driving and identification privileges granted by the document are no longer valid. (MMDDCCYY for U.S., CCYYMMDD for Canada) | DBA |
| lastName | Family name of the cardholder. (Family name is sometimes also called “last name” or “surname.”) | DAB/DCS |
| firstName | First name of the cardholder. | DAC |
| middleName | Middle name(s) of the cardholder. | DAD |
| issuedDate | Date on which the document was issued.(MMDDCCYY for U.S., CCYYMMDD for Canada) | DBD |
| birthDate | Date on which the cardholder was born.(MMDDCCYY for U.S., CCYYMMDD for Canada) | DBB |
| sex | Gender of the cardholder. 1 = male, 2 = female, 9 = not specified. | DBC |
| eyeColor | Color of cardholder's eyes. | DAY |
| height | Height of cardholder. Inches (in): number of inches followed by " in" ex. 6'1'' = "073 in" Centimeters (cm): number of centimeters followed by " cm" ex. 181 centimeters="181 cm" | DAV/DAU |
| addressStreet_1 | Street portion of the cardholder address. | DAG |
| addressCity | City portion of the cardholder address. | DAI |
| addressJurisdictionCode | State portion of the cardholder address. | DAJ |
| addressPostalCode | Postal code portion of the cardholder address in the U.S. and Canada. | DAK |
| licenseNumber | The number assigned or calculated by the issuing authority. | DAI |
| documentDiscriminator | Number must uniquely identify a particular document issued to that customer from others that may have been issued in the past. | DCF |
| issuingCountry | Country in which DL/ID is issued. U.S. = USA, Canada = CAN. | DCG |
| familyNameTruncation | A code that indicates whether a field has been truncated (T), has not been truncated (N), or – unknown whether truncated (U). | DDE |
| firstNameTruncation | A code that indicates whether a field has been truncated (T), has not been truncated (N), or – unknown whether truncated (U). | DDF |
| middleNameTruncation | A code that indicates whether a field has been truncated (T), has not been truncated (N), or – unknown whether truncated (U). | DDG |
| addressStreet_2 | Second line of street portion of the cardholder address. | DAH |
| hairColour | Bald, black, blonde, brown, gray, red/auburn, sandy, white, unknown. If the issuing jurisdiction wishes to abbreviate colors, the three-character codes provided in AAMVA D20 must be used. | DAZ |
| birthPlace | Country and municipality and/or state/province. | DCI |
| auditInfo | A string of letters and/or numbers that identifies when, where, and by whom a driver license/ID card was made. | DCJ |
| inventoryControlNumber | A string of letters and/or numbers that is affixed to the raw materials (card stock, laminate, etc.) used in producing driver licenses and ID cards.(DHS recommended field) | DCK |
| nameAlias | ALTERNATIVE NAME(S) of the individual holding the Driver License or ID. | DBN |
| lastNameAlias | Other family name by which cardholder is known. | DBO/DBN |
| givenNameAlias | Other given name by which cardholder is known. | DBG |
| suffixAlias | Other suffix by which cardholder is known. | DBR/DBS |
| suffix | Name Suffix (If jurisdiction participates in systems requiring name suffix (PDPS, CDLIS, etc.), the suffix must be collected and displayed on the DL/ID and in the MRT). | DAE/DCU |
| weightRange | Indicates the approximate weight range of the cardholder:
0 = up to 31 kg (up to 70 lbs)
1 = 32 – 45 kg (71 – 100 lbs)
2 = 46 - 59 kg (101 – 130 lbs)
3 = 60 - 70 kg (131 – 160 lbs)
4 = 71 - 86 kg (161 – 190 lbs)
5 = 87 - 100 kg (191 – 220 lbs)
6 = 101 - 113 kg (221 – 250 lbs)
7 = 114 - 127 kg (251 – 280 lbs)
8 = 128 – 145 kg (281 – 320 lbs)
9 = 146+ kg (321+ lbs) | DCE |
| race | Codes for race or ethnicity of the cardholder, as defined in AAMVA D20. | DCL |
| standardVehicleCode | Standard vehicle classification code(s) for cardholder. | DCM |
| standardEndorsementsCode | Standard endorsement code(s) for cardholder. | DCN |
| standardRestrictionCode | Standard restriction code(s) for cardholder. | DCO |
| jurisdictionVehicleCodeDescription | Text that explains the jurisdiction-specific code(s) for classifications of vehicles cardholder is authorized to drive. | DCP |
| jurisdictionEndorsementsCodeDescription | Text that explains the jurisdiction-specific code(s) that indicates additional driving privileges granted to the cardholder beyond the vehicle class. | DCQ |
| jurisdictionRestrictionCodeDescription | Text describing the jurisdiction-specific restriction code(s) that curtail driving privileges. | DCR |
| complianceType | DHS required field that indicates compliance: “F” = compliant; and, “N” = non-compliant. | DDA |
| revisionDate | DHS required field that indicates date of the most recent version change or modification to the visible format of the DL/ID. (MMDDCCYY for U.S., CCYYMMDD for Canada) | DDB |
| hazmatExpirationDate | Date on which the hazardous material endorsement granted by the document is no longer valid. (MMDDCCYY for U.S., CCYYMMDD for Canada) | DDC |
| isTemporaryDocument | DHS required field that indicates that the cardholder has temporary lawful status = “1”. | DDD |
| Weight(pounds) | Cardholder weight in pounds Ex. 185 lb = “185” | DAW |
| Weight(kilograms) | Cardholder weight in kilograms Ex. 84 kg = “084” | DAX |
| under18Until | Date on which the cardholder turns 18 years old. (MMDDCCYY for U.S., CCYYMMDD for Canada) | DDH |
| under19Until | Date on which the cardholder turns 19 years old. (MMDDCCYY for U.S., CCYYMMDD for Canada) | DDI |
| under21Until | Date on which the cardholder turns 21 years old. (MMDDCCYY for U.S., CCYYMMDD for Canada) | DDJ |
| isOrganDonor | Field that indicates that the cardholder is an organ donor = “1” | DDK |
| isVeteran | Field that indicates that the cardholder is a veteran = “1” | DDL |
| commercialVehicleCode | Federally established codes for vehicle categories, endorsements, and restrictions that are generally applicable to commercial motor vehicles. If the vehicle is not a commercial vehicle, "NONE" is to be entered. | DCH |
| givenName | Given names of the cardholder. (Given names include all names other than the Family Name. This includes all those names sometimes also called “first” and “middle” names.) | DCT |


