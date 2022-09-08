---
layout: default-layout
title: Supported code types - Dynamsoft Code Parser SDK 
description: This is the supported code types page of Dynamsoft Label Recoginizer SDK.
keywords: code types
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# ICAO VDS-NC Health Proof

The ICAO VDS-NC (Visible Digital Seal for non-constrained environments) specifications detail two versions for the Proof of Vaccination. Only version 1 is supported. Following tables show what fields could be contained in a VDS-NC Qr code's parse result:

| FieldName | Definition |
|---|---|
| version | Each of the use cases will define a version number for the structure. In case of changes in structure, the version number will be incremented. |
| type | Type is set to “icao.test” for PoT (data defined by CAPSCA), “icao.vacc” for PoV (data defined by WHO), “icao.rcvy” for PoR (data defined by CAPSCA). Other Types may be added in the future. |
| issuingCountry | A three letter code identifying the issuing state or organization. The three letter code is according to Doc 9303-3. |
| dateOfBirth | Vaccinated person’s date of birth.  |
| identifierNum | Any other document number at discretion of issuer |
| name | Notation, Full MRZ Name. |
| sex | Sex of the holder (as specified in Doc 9303-4 Section 4.1.1.1 – Visual Inspection Zone). |
| UniqueVaccinationCertificateIdentifier | A unique string stands for the vaccination certificate. |
| vaccineOrProphylaxis | ICD-11 Extension codes (http://id.who.int/icd/entity/164949870). |
| diseaseOrAgentTargeted | Disease or agent that the vaccination provides protection against. |
| vaccineBrand | Vaccine medicinal product. |
| administeringCentre | Name/code of administering centre or a health authority responsible for the vaccination event. |
| countryOfVaccination | The country in which the individual has been vaccinated. |
| dateOfVaccination | Date on which the vaccine was administered. The ISO8601 full date format YYYY-MM-DD MUST be used. |
| vaccineBatchNumber | A distinctive combination of numbers and/or letters which specifically identifies a batch. |
| doseNumber | Vaccine dose number. |
| signatureAlgorithm | The signature algorithm used to produce the signature. Signatures MUST be ECDSA. A key length of 256 bit in combination with SHA-256(at the time this document is created) is RECOMMENDED. |
| certificate | X.509 signer certificate in base64url [RFC 4648]. |
| signatureValue | Signature value signed over the Data in base64url [RFC 4648]. |