---
layout: default-layout
title: Template Structure - Dynamsoft Code Parser SDK 
description: This is the template structure page of Dynamsoft Label Recoginizer SDK.
keywords: template structure
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
breadcrumbText: template structure
---

# Template Structure

Dynamsoft Code Parser (DCP) starts to provide user-customized parsing feature since edition 2.x by configuring a JSON template of the code's parsing rule. This article introduces how to configure a JSON template to make the CodeParser capable of parsing any code as long as its parsing spedification is available and accurate.

## Definition

Dynamsoft Code Parser uses a code parsing rule template to set parameters. A template contains four types of data: `Specification`, `DedicatedLibrary`, `CodeMapFile` and `FieldArray`.

- `Specification` is used to specify the official released specification which the parsing rule comes from or relies on. Read more about [`Specification`](#specification);

- `FieldArray` is an array used to specify all the fields you want to parse from code. Every field in this array should be assigned with `FieldName` and `ParentFieldName`. Read more about [`FieldArray`](#fieldarray).

- `DedicatedLibrary` is an optional parameter used to specify the path of a dynamic-link library which is provided by us. Please reach out on us if you have some special code to parse.

- `CodeMapFile` is an optional parameter used to specify the path of a map that helps converting some fields which represented as code into readable results.

### Specification

Each parsing rule template must specify its referenced specification through the `Specification` object. Its parameters includes: 

- `Name` specifies the specification's name uniquely.

- `BasedOn` is an optional parameter used to specify the name of which existing specification your new parsing rule template is based on. It can save you time on new template's writing.

- `CodeType` specifies the code's type. Each `CodeType` can be assigned to several specific specifications. It can be used as the argument of [`setCodeType()`](../development/javascript/api-reference/CodeParser-v2.0.0.md#setcodetype);

- `FeatureString` is a regular expression string used to distinguish between all specifications under one `CodeType`.

### FieldArray

`FieldArray` is an array of objects. Each object stands for a field in the code that you want to parse. Parameters in each object are as follows:

- `FieldName` identifies the field uniquely and represent the parse result of the field.

- `ParentFieldName` specifies the field which contains the current field. It's used with `OffsetFromParentStart` to locate the current field. If the code string needs some processing, you can define it with `fullCodeString` as its `FieldName`. If not, the field of `fullCodeString` still exists.

- `Location` is an object that contains an array which stores all the options to locate the field and a string which specify the way to apply these options.

    - `Options` is an array that includes all the optional location ways. Normal location options are as follows:

    Option 1: `OffsetFromParentStart` and `Length`
    ```json
    {
        "OffsetFromParentStart": 0,
        "Length": 0,
        "SecondLocation": {
            //...
        }
    }
    ```
    Option 2: `OffsetFromParentStart` and `RegExString`
    ```json
    {
        "OffsetFromParentStart": 0,
        "RegExString": ""
    }
    ```
    Option 3: `PreviousFieldName`, `OffsetFromPreviousEnd` and `Length`
    ```json
    {
        "PreviousFieldName": "",
        "OffsetFromPreviousEnd": 0,
        "Length": 0
    }
    ```
    Option 4: `PreviousFieldName`, `OffsetFromPreviousEnd` and `RegExString`
    ```json
    {
        "PreviousFieldName": "",
        "OffsetFromPreviousEnd": 0,
        "RegExString": ""
    }
    ```
    Option 5: `StartSeparator` and `EndSeparator`
    ```json
    {
        "StartSeparator": "DAA",
        "EndSeparator": " "
    }
    ```
    Option 6: `OffsetFromParentStart` and `EndSeparator`
    ```json
    {
        "OffsetFromParentStart": 0,
        "EndSeparator": ""
    }
    ```
    Option 7: `PreviousFieldName`, `OffsetFromPreviousEnd` and `EndSeparator`
    ```json
    {
        "PreviousFieldName": "",
        "OffsetFromPreviousEnd": 0,
        "EndSeparator": ""
    }
    ```
    Option 8: `XmlKey` specifies each field's key in xml code.
    ```json
    {
        "XmlKey": ""
    }
     ```
    Option 9: `JsonKey` specifies each field's key in json code.
    ```json   
    {
        "JsonKey": ""
    }
    ```
    
    - `OptionCombinationType` has two optional string values: `PriorityOrder` and `MutualVerification`. `PriorityOrder` is default value and means to apply only one location option from `Options` in array order. `MutualVerification` means to apply all the options from `Options` and check whether their results are the same to verify whether parsing succeeded.

- `ParseFunctionName` is an optional string parameter used to specify the name of the function which can parse the field after location. It's only used when above location parameters can't parse out the field and `DedicatedLibrary` is already specified.

- `DecryptionKey` is an optional object parameter used to specify the decryption type and key of the decryted field. 

    - `Type` specifies the decryption type.

    - `Value` specifies the decryption key.

- `CodeMapSectionName` is an optional string parameter used to specify the name of map section which can convert the field into readable result.

## Template Example

Below shows a part from MRZ-TD1's parsing rule template:

```json
{
    "Specification": {
        "Name": "MRZ-TD1", 
        "FeatureString": "^[ACI][A-Z\\d<]{89}$",
        "CodeType": "CT_MRZ"
    },
    "FieldArray": [
        {
            "FieldName": "Line1",
            "ParentFieldName": "fullCodeString",
            "Location": {
                "Options": [
                    {
                        "OffsetFromParentStart": 0,
                        "Length": 30
                    }
                ]
            }
        },
        {
            "FieldName": "documentCode",
            "ParentFieldName": "Line1",
            "Location": {
                "Options": [
                    {
                        "OffsetFromParentStart": 0,
                        "Length": 2
                    }
                ]
            }
        },
        {
            "FieldName": "issuingState",
            "ParentFieldName": "Line1",
            "Location": {
                "Options": [
                    {
                        "PreviousFieldName": "documentCode",
                        "OffsetFromPreviousEnd": 0,
                        "Length": 3,
                        "RegExString": "[A-Z]{1,3}"
                    }
                ]
            }
        },
        {
            "FieldName": "documentNumber",
            "ParentFieldName": "Line1",
            "Location": {
                "Options": [
                    {
                        "PreviousFieldName": "issuingState",
                        "OffsetFromPreviousEnd": 0,
                        "Length": 9,
                        "RegExString": "[A-Z0-9]{1,9}"
                    }
                ]
            }
        },
        {
            "FieldName": "checkDigitForDocumentNumber",
            "ParentFieldName": "Line1",
            "Location": {
                "Options": [
                    {
                        "PreviousFieldName": "documentNumber",
                        "OffsetFromPreviousEnd": 0,
                        "Length": 1
                    }
                ]
            }
        },
        {
            "FieldName": "optionalData1",
            "ParentFieldName": "Line1",
            "Location": {
                "Options": [
                    {
                        "PreviousFieldName": "checkDigitForDocumentNumber",
                        "OffsetFromPreviousEnd": 0,
                        "Length": 15,
                        "RegExString": "/[A-Z0-9]{1,15}/g"
                    }
                ]
            }
        },
        {
            "FieldName": "Line2",
            "ParentFieldName": "fullCodeString",
            "Location": {
                "Options": [
                    {
                        "PreviousFieldName": "Line1",
                        "OffsetFromPreviousEnd": 0,
                        "Length": 30
                    }
                ]
            }
        }
        //...
    ]
}
```
> Note
> If you have any question about the template, please feel free to contact us.
