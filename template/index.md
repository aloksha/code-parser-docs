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

Dynamsoft Code Parser(DCP) 2.0.0 starts to support parsing any type of code by loading its parse rule templates. This article will introduce you what a parse rule template includes and how to write a template.

## Definition

Dynamsoft Code Parser uses parse rule templates to support code parsing. A template contains 6 types of data: 

- `Name`
- `CodeType`
- `CodeFeaturePattern`
- `DedicatedLibrary`
- `CodeMapFile`
- `Fields`

### `Name` 

    Specifies the template's name uniquely which always consists of the name of the specification that the template refered to.

### `CodeType` 

    Specifies the code's type. One `CodeType` can cover several specifications. It can be used as the argument of [`setCodeType()`](../development/javascript/api-reference/CodeParser.md#setcodetype);

### `CodeFeaturePattern` 

    A regular expression string used to find out whether the code follows this template.

### `DedicatedLibrary` 

    An optional parameter used to specify the path of a dynamic-link library which is provided by us. Please [contact us](https://www.dynamsoft.com/company/contact/) if you have any special code to parse.

### `CodeMapFile` 

    An optional parameter used to specify the path of a map that helps converting some fields which represented as code into readable results.

### Fields

    An array of objects used to specify all the fields you want to parse from code. Each object stands for a field in the code that you want or need to parse. Parameters in each object are as follows:

- `FieldName` identifies the field uniquely and represent the parse result of the field.

- `ChildFields` specifies the field which contains the current field. It's used with `OffsetFromParentStart` to locate the current field. If the code string needs some processing, you can define it with `fullCodeString` as its `FieldName`. If not, the field of `fullCodeString` still exists.

- `Location` is an object that contains an array which stores all the options to locate the field and a string which specify the way to apply these options.

    - `Options` is an array that includes all the optional location ways. Normal location options are as follows:

    Option 1: `OffsetFromParentStart` and `Length`
    ```json
    {
        "OffsetFromParentStart": 0,
        "Length": 0
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
    Option 10: If one-time location can't finish parsing, you can add a `SecondLocation` after its first location.
    ```json
    {
        "OffsetFromParentStart": 0,
        "Length": 0,
        "SecondLocation": {
            //...
            "RegExString": "/[A-Z]{1,}/g"
        }
    }
    ```
    
    - `OptionCombinationType` has two optional string values: `PriorityOrder`(default value) and `MutualVerification`. 

        `PriorityOrder` means to apply only one location option from `Options` array, and the array order is also the priority order.

        `MutualVerification` means to apply all the options from `Options` array and check whether their results are the same to verify whether parsing succeeded.

- `ParseFunctionName` is an optional string parameter used to specify the name of the function which can parse the field after location. It's only used when above location parameters can't parse out the field and `DedicatedLibrary` is already specified.

- `DecryptionKey` is an optional object parameter used to specify the decryption type and key of the decryted field. 

    - `Type` specifies the decryption type.

    - `Value` specifies the decryption key.

- `CodeMapTableName` is an optional string parameter used to specify the name of map table which can convert the field into readable result.

- `Verification` is an optional object parameter used to specify how to verify the field. It can be written in folowing two ways:

    Way 1: checksum verification
    ```json
    "Verification": {
        "Type": "checksum",
        "CheckDigit": "fieldNameOfCheckDigit",
        "VerificationFunctionName": ""
    }
    ```
    Way 2: certificate verification
    ```json
    "Verification": {
        "Type": "certification",
        "Cert": "",
        "VerificationFunctionName": ""
    }
    ```

## Template Example

Below shows a part from MRZ-TD1's parse rule template:

```json

```
> If you have any question about the template, please feel free to [contact us](https://www.dynamsoft.com/company/contact/).
