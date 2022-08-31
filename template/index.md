---
layout: default-layout
title: Template Structure - Dynamsoft Code Parser SDK 
description: This is the template structure page of Dynamsoft Label Recoginizer SDK.
keywords: Template Structure
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Template Structure
---

# Template Structure

Dynamsoft Code Parser(DCP) 2.0.0 starts to support parsing any type of code by adding code's parsing templates. This article will introduce you what a parsing template includes and how to write a template.

## Definition

Dynamsoft Code Parser uses parse rule templates to support code parsing. A template contains 6 types of data: 

- `Name`
- `CodeType`
- `CodeFeaturePattern`
- `DedicatedLibrary`
- `CodeMapFile`
- `Fields`


### Name

A required and unique name of the template which usually named after the specification's name that the template based on. 

### CodeType 

A required string used to symbolize the code's type so that it can be used when designating what code type you want to parse. See API [`setCodeType()`](../development/javascript/api-reference/CodeParser.md#setcodetype) for more details. One `CodeType` can be designated to several templates since it's quite common that the same code could follow different specifications.

### CodeFeaturePattern 

A regular expression pattern string which describes the features of the code that the template can parse. It's required when the code is a string and you have two or more templates under one `CodeType`.

### DedicatedLibrary 

An optional parameter used to specify the path of a dynamic-link library which is used to turn the code into plain text if the code is in unreadable formats such as byte array. Please [contact us](https://www.dynamsoft.com/company/contact/) if you have special code to parse.

### CodeMapFile 

An optional parameter used to specify the path of a map that helps converting some fields which represented as code into readable results.

### Fields

An array of objects used to specify all the fields you want to parse from code. Each object stands for a field in the code that you want or need to parse. Parameters in each field are as follows:

- `FieldName` identifies the field uniquely and corresponds to the `FieldName` in `[ParseField](../development/javascript/api-reference/interface/ParseField.md)`. The full code in plain text is also seen as a field and it uses "fullCode" as `FieldName`. If the raw code needs to be processed to get the plain text, then the processed result is the "fullCode".

- `ChildFields` specifies the fields that contained in the current field. 

- `Location` is an object that contains an array which stores all the options to locate the field and a string which specify the way to apply these options.

    - `Options` is an array that includes all the optional location ways. Normal location options are as follows:

    Option 1: specify the start position's offset from another field and the length of the field.
    ```json
    {
        "OffsetFromField": "",
        "Offset": 0,
        "Length": 0
    }
    ```
    Option 2: specify the start position's offset from another field and the RegExString of the field.
    ```json
    {
        "OffsetFromField": "",
        "Offset": 0,
        "RegExString": ""
    }
    ```
    Option 3: specify the separator before the start position and the length of the field.
    ```json
    {
        "StartSeparator": "AAMVA",
        "Length": 6
    }
    ```
    Option 4: specify the separator before the start position and the RegExString of the field.
    ```json
    {
        "StartSeparator": "AAMVA",
        "RegExString": ""
    }
    ```
    Option 5: specify the start position's offset from another field and the separator after the field.
    ```json
    {
        "OffsetFromField": "",
        "Offset": 0,
        "EndSeparator": ""
    }
    ```
    Option 6: specify the separators before and after the field.
    ```json
    {
        "StartSeparator": "DAA",
        "EndSeparator": " "
    }
    ```
    Option 7: specify the start position's offset of the field and the end character of the field.
    ```json
    {
        "OffsetFromField": "",
        "Offset": 0,
        "EndWith": ""
    }
    ```
    Option 8: specify the separator before the field and the end character of the field.
    ```json
    {
        "StartSeparator": "DAA",
        "EndWith": " "
    }
    ```
    Option 9: specify the start character and the end character of the field.
    ```json
    {
        "StartWith": ";",
        "EndWith": "?"
    }
    ```
    Option 10: specify the start character of the field and its offset from another field and the end character of the field.
    ```json
    {
        "OffsetFromField": "track1",
        "Offset": 0,
        "StartWith": ";",
        "EndWith": "?"
    }
    ```
    Option 11: specify the end separator after the field and the length of the field.
    ```json
    {
        "EndSeparator": " ",
        "Length": 6
    }
    ```
    Option 12: If one-time location can't finish parsing, you can add a `SecondLocation` after its first location.
    ```json
    {
        //...
        "SecondLocation": {
            "RegExString": "/[A-Z]{1,}/g"
        }
    }
    ```
    Option 13: `XmlKey` specifies each field's key in xml code.
    ```json
    {
        "XmlKey": ""
    }
     ```
    Option 14: `JsonKey` specifies each field's key in json code.
    ```json   
    {
        "JsonKey": ""
    }
    ```
    
    - `OptionCombinationType` has 4 optional string values: `PriorityOrder`(default value), `MutualVerification`, `Voting` and `Concatenation`. 

        1. `PriorityOrder` means to apply only one location option from `Options` array, and the array order is also the priority order.

        2. `MutualVerification` means to apply all the options from `Options` array and check whether their results are the same to verify whether parsing succeeded.

        3. `Voting` means to apply all the options from `Options` array and use the result which shows more.

        4. `Concatenation` means to apply all the options from `Options` array and concatenate all the results together as the final result.

- `ParseFunctionName` is an optional string parameter used to specify the name of the function which can process the code before its fields' location. It's only used when the fields in the code can't be located according to the raw code.

- `Decryption` is an optional object parameter used to specify the encryption algorithm and the decryption key. 

    - `Algorithm` specifies the encryption algorithm.

    - `Key` specifies the decryption key.

- `CodeMapTableName` is an optional string parameter used to specify the name of map table which can convert the field into readable result.

- `Verification` is an optional object parameter used to specify how to verify the field. It can be written in folowing two ways:

    Way 1: checksum verification
    ```json
    "Verification": {
        "Type": "checksum",
        "CheckDigit": "fieldNameOfCheckDigit", //the field's name of the check digit
        "VerificationFunctionName": ""         //the name of the verification function in the dynamic-link library
    }
    ```
    Way 2: certificate verification
    ```json
    "Verification": {
        "Type": "certification",
        "Cert": "pathOfTheCertificate", //the path of the certificate that used to verify
        "VerificationFunctionName": ""  //the name of the verification function in the dynamic-link library
    }
    ```

## Template Example

Below shows a part from "MRZ-TD1" parsing template:

```json
{
    "Name": "MRZ-TD1", 
    "CodeType": "CT_MRZ",
    "CodeFeaturePattern": "^[ACI][A-Z\\d<]{89}$",
    "DedicatedLibrary": "DCP_DLL",
    "Fields": [
        {
            "FieldName": "fullCode",
            "ChildFields": [
                {
                    "FieldName": "Line1",
                    "Location": {
                        "Options": [
                            {
                                "OffsetFromField": "fullCode",
                                "Offset": 0,
                                "Length": 30
                            }
                        ]
                    },
                    "ChildFields": [
                        {
                            "FieldName": "documentCode",
                            "Location": {
                                "Options": [
                                    {
                                        "OffsetFromField": "Line1",
                                        "Offset": 0,
                                        "Length": 2
                                    }
                                ]
                            }
                        },
                        {
                            "FieldName": "issuingState",
                            "Location": {
                                "Options": [
                                    {
                                        "OffsetFromField": "Line1",
                                        "Offset": 2,
                                        "Length": 3,
                                        "SecondLocation": {
                                            "RegExString": "[A-Z]{1,3}"
                                        }
                                    }
                                ]
                            }
                        },
                        {
                            "FieldName": "documentNumber",
                            "Location": {
                                "OptionCombinationType": "Concatenation",
                                "Options": [
                                    {
                                        "OffsetFromField": "Line1",
                                        "Offset": 5,
                                        "Length": 9,
                                        "SecondLocation": {
                                            "RegExString": "[A-Za-z0-9]{1,9}"
                                        }
                                    },
                                    {
                                        "OffsetFromField": "Line1",
                                        "Offset": 15,
                                        "Length": 13,
                                        "SecondLocation": {
                                            "RegExString": "[A-Za-z0-9]{1,13}"
                                        }
                                    }
                                ]
                            },
                            "Verification": {
                                "Type": "checksum",
                                "CheckDigit": "checkDigitForDocumentNumber",
                                "VerificationFunctionName": "MRZ_verification"
                            }
                        },
                        {
                            "FieldName": "checkDigitForDocumentNumber",
                            "Location": {
                                "Options": [
                                    {
                                        "OffsetFromField": "Line1",
                                        "Offset": 14,
                                        "Length": 1,
                                        "SecondLocation": {
                                            "RegExString": "[0-9]"
                                        }
                                    },
                                    {
                                        "OffsetFromField": "Line1",
                                        "Offset": 16,
                                        "Length": 2,
                                        "SecondLocation": {
                                            "RegExString": "[0-9]"
                                        }
                                    }
                                ]
                            }
                        }
                        //...
                        //The rest of this template are left out here.
                    ]
                }
            ]
        }
    ]
}
```
> If you have any question about the template, please feel free to [contact us](https://www.dynamsoft.com/company/contact/).
