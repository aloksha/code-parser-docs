---
layout: default-layout
title: Release Notes v2.x - Dynamsoft Code Parser JavaScript SDK
description: This is the release notes page for Dynamsoft Code Parser JavaScript SDK v2.x.
keywords: release notes, javascript
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for JavaScript SDK - 2.x

## 2.0.0 (0//2022)

### Add

* Add `CT_MRZ`, `CT_VIN`, `CT_VDS_NC` to EnumCodeFormat.
* Add `RIT_MRZ`, `RIT_VIN`, `RIT_OTHER` to EnumResultInfoType.
* Add some new enums to [EnumErrorCode](../api-reference/enum/EnumErrorCode.md).

### Change

* Change `CF_DL_AAMVA_ANSI` to `CF_DL_AAMVA`.
* Change `RIT_DRIVER_LICENSE_INFO` to `RIT_DRIVER_LICENSE_AAMVA` and `RIT_DRIVER_LICENSE_SOUTH_AFRICA`.
* Change `RIT_PERSONAL_ID_INFO` to `RIT_PERSONAL_ID`.
* Change `RIT_VDSNC_INFO` to `RIT_VDSNC`.

### New

* New property `license` to control license of DCP.
* New property `engineResourcePath` to specify the path of DCP WASM engine.
* New `loadWasm()` to `CodeParser` to load and compile the WASM.

