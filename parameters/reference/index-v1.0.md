---
layout: default-layout
title: Dynamsoft Code Parser Parameter Reference - Main Page
description: Dynamsoft Code Parser Parameter Reference - Main Page
keywords: parameter reference, parameters, LabelRecognitionParameter, ReferenceRegion, TextArea, LineSpecification, CharacterModel
needAutoGenerateSidebar: true
needGenerateH3Content: true
---


# Dynamsoft Code Parser SDK - Parameters


## LabelRecognitionParameter Object

 | Parameter Name | Description |
 | -------------- | ----------- | 
 | [`LabelRecognitionParameter.Name`](code-parser-parameter/parameter-control.md#name) | The name of the LabelRecognitionParameter object. |
 | [`LabelRecognitionParameter.BinarizationModes`](code-parser-parameter/binarization-modes.md#binarizationmodes) | 	Sets the mode and priority for binarization. |
 | [`LabelRecognitionParameter.CharacterModelName`](code-parser-parameter/parameter-control.md#charactermodelname) | Sets the name of a white list of recognizable characters. |
 | [`LabelRecognitionParameter.GrayscaleTransformationModes`](code-parser-parameter/grayscale-transformation-modes.md#grayscaletransformationmodes) | Sets the mode and priority for the grayscale image conversion. |
 | [`LabelRecognitionParameter.LetterHeightRange`](code-parser-parameter/parameter-control.md#letterheightrange) | Sets the range of letter height (in pixel or a percentage value relative to the height of the text area). |
 | [`LabelRecognitionParameter.LinesCount`](code-parser-parameter/parameter-control.md#linescount) | Sets the text lines count of the text area. |
 | [`LabelRecognitionParameter.LineStringRegExPattern`](code-parser-parameter/parameter-control.md#linestringregexpattern) | Specifies the regular expression pattern of each line string text in current image to recognize. |
 | [`LabelRecognitionParameter.MaxThreadCount`](code-parser-parameter/parameter-control.md#maxthreadcount) | Sets the maximum number of threads the algorithm will use to recognize text. |
 | [`LabelRecognitionParameter.ReferenceRegionNameArray`](code-parser-parameter/parameter-control.md#referenceregionnamearray) | The name array of the ReferenceRegion object(s). |
 | [`LabelRecognitionParameter.RegionPredetectionModes`](code-parser-parameter/region-predetection-modes.md#regionpredetectionmodes) | Sets the region pre-detection mode for barcodes search. |
 | [`LabelRecognitionParameter.TextRegExPattern`](code-parser-parameter/parameter-control.md#textregexpattern) | Specifies the regular expression pattern of the text to recognize. |


## ReferenceRegion Object

 | Parameter Name | Description |
 | -------------- | ----------- | 
 | [`ReferenceRegion.Name`](reference-region/parameter-control.md#name) | The name of the ReferenceRegion object. |
 | [`ReferenceRegion.Localization`](reference-region/localization.md#localization) | The localization of the reference region(s). |
 | [`ReferenceRegion.TextAreaNameArray `](reference-region/parameter-control.md#textareanamearray ) | Specifies the name array of the TextAreas which is relative to current reference region. |

## TextArea Object

 | Parameter Name | Description |
 | -------------- | ----------- | 
 | [`TextArea.Name`](text-area/parameter-control.md#name) | The name of the TextArea object. |
 | [`TextArea.FirstPoint`](text-area/parameter-control.md#firstpoint) | The first point of the text area, which is usually the top-left corner. |
 | [`TextArea.SecondPoint`](text-area/parameter-control.md#secondpoint) | The second point of the text area, which is usually the top-right corner. |
 | [`TextArea.ThirdPoint`](text-area/parameter-control.md#thirdpoint) | The third point of the text area, which is usually the bottom-right corner. |
 | [`TextArea.FourthPoint`](text-area/parameter-control.md#fourthpoint) | The fourth point of the text area, which is usually the bottom-left  corner. |
 | [`TextArea.CharacterModelName`](text-area/parameter-control.md#charactermodelname) | Sets the name of a white list of recognizable characters. |
 | [`TextArea.GrayscaleTransformationModes`](text-area/parameter-control.md#grayscaletransformationmodes) | Sets the mode and priority for the grayscale image conversion. |
 | [`TextArea.LetterHeightRange`](text-area/parameter-control.md#letterheightrange) | Sets the range of letter height (in pixel or a percentage value relative to the height of the text area). |
 | [`TextArea.LinesCount`](text-area/parameter-control.md#linescount) | Sets the text lines count of the text area. |
 | [`TextArea.LineSpecificationNameArray `](text-area/parameter-control.md#LineSpecificationnamearray ) | Specifies the name array of the LineSpecification objects which is relative to current TextArea. |
 | [`TextArea.LineStringRegExPattern`](text-area/parameter-control.md#linestringregexpattern) | Specifies the regular expression pattern of each line string text in current text area to recognize. |
 | [`TextArea.TextAreaNameArray `](text-area/parameter-control.md#textareanamearray ) | Specifies the name array of the TextAreas which is relative to current text area. |
 | [`TextArea.TextRegExPattern`](text-area/parameter-control.md#textregexpattern) | Specifies the regular expression pattern of the text to recognize. |


## LineSpecification Object

 | Parameter Name | Description |
 | -------------- | ----------- | 
 | [`LineSpecification.Name`](line-specification/parameter-control.md#name) | The name of the LineSpecification object. |
 | [`LineSpecification.CharacterModelName`](line-specification/parameter-control.md#charactermodelname) | Sets the name of a white list of recognizable characters. |
 | [`LineSpecification.LineNumber`](line-specification/parameter-control.md#linenumber) | The line number of the line targeted by the LineSpecification object. |
 | [`LineSpecification.LineStringRegExPattern`](line-specification/parameter-control.md#linestringregexpattern) | Specifies the regular expression pattern of the string within a line. |

## CharacterModel Object

 | Parameter Name | Description |
 | -------------- | ----------- | 
 | [`CharacterModel.Name`](character-model/parameter-control.md#name) | The name of the CharacterModel object. |
 | [`CharacterModel.DirectoryPath`](character-model/parameter-control.md#directorypath) | The path of the folder containing the character model files. |
 | [`CharacterModel.FilterFilePath`](character-model/parameter-control.md#filterfilepath) | The full path of the filter file which specifies the characters to be recognized. |



## Organizational Json Parameter

 | Parameter Name | Description |
 | -------------- | ----------- | 
 | [`LabelRecognitionParameterArray`](organizational-json-parameter.md#labelrecognitionparameterarray) | An array of LabelRecognitionParameter objects. |
 | [`ReferenceRegionArray`](organizational-json-parameter.md#referenceregionarray) | An array of ReferenceRegionArray objects. |
 | [`TextAreaArray`](organizational-json-parameter.md#textareaarray) | An array of TextArea objects. |
 | [`LineSpecificationArray`](organizational-json-parameter.md#linespecificationarray) | An array of LineSpecification objects. |
 | [`CharacterModelArray`](organizational-json-parameter.md#charactermodelarray) | An array of CharacterModel objects. |
