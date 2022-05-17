---
layout: default-layout
title: Dynamsoft Code Parser Parameter Reference for CharacterModel Object
description: This page shows Dynamsoft Code Parser Parameter Reference for CharacterModel Object.
keywords: CharacterModel, parameter reference, parameter
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# CharacterModel Object

 | Parameter Name | Description |
 | -------------- | ----------- | 
 | [`CharacterModel.Name`](#name) | The name of the CharacterModel object. |
 | [`CharacterModel.DirectoryPath`](#directorypath) | The path of the folder containing the character model files. |
 | [`CharacterModel.FilterFilePath`](#filterfilepath) | The full path of the filter file which specifies the characters to be recognized. |

---


## Name
The name of the CharacterModel object.  

**Remarks**    
It must be a unique name.  
A CharacterModel is consisted by the following three files:  
[Name].txt,  
[Name].prototxt,  
[Name].caffemodel  
And optionally, it can have some assisted CharacterModels with formatted file names like:  
[Name]_Assist_[SubName].txt  
[Name]_Assist_[SubName].prototxt  
[Name]_Assist_[SubName].caffemodel  
Note: [Name] is current value and [SubName] can be customized by you own.


**As Json Parameter**

| Json Object |	Json Parameter Name | Value Type | Default Value |
| ----------- | ------------------- | ---------- | ------------- |
| CharacterModel | Name | *string* | It must be a mandatory setting value. |

**Json Parameter Example**   
```json
{
    "Name":"CharacterModel1"
}
```




## DirectoryPath
The path of the folder containing the character model files.  


**As Json Parameter**

| Json Object |	Json Parameter Name | Value Type | Default Value |
| ----------- | ------------------- | ---------- | ------------- |
| CharacterModel | DirectoryPath | *string* | "" |

**Json Parameter Example**   
```json
{
    "DirectoryPath":"C:/CharacterModelFiles"
}
```




## FilterFilePath
The full path of the filter file which specifies the characters to be recognized.  

**As Json Parameter**

| Json Object |	Json Parameter Name | Value Type | Default Value |
| ----------- | ------------------- | ---------- | ------------- |
| CharacterModel | FilterFilePath | *string* | "" |

**Json Parameter Example**   
```json
{
    "FilterFilePath":"C:/CharacterModelFiles/CM1_F1.txt"
}
```




