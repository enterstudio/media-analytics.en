---
description: null
seo-description: null
seo-title: Implementation for standard ad metadata
title: Implementation for standard ad metadata
uuid: 56b1f817-51c3-4874-9055-4936f41b51fd
index: y
internal: n
snippet: y
translate: y
---

# Implementation for standard ad metadata

Here is the Standard Metadata Constants reference: 

|  Constant name  | Description  |
|---|---|
|  ` ADBMediaObjectKeyStandardVideoMetadata`  | Constant for attaching standard video metadata on ` MediaInfo` ` ADBMediaObject`  |
|  ` ADBMediaObjectKeyStandardAdMetadata`  | Constant for attaching standard ad metadata on ` AdInfo` ` ADBMediaObject`  |


>1. Create a dictionary of standard Ad metadata key value pairs using the ` ADBStandardMetadataKeys` specified above.
>1. Set the standard ad metadata dictionary on ` AdObject` ` ADBMediaObject` instance using the Standard Metadata constant for ad metadata.
>1. Provide this ` AdObject` while invoking ` trackEvent` API for ` ADBMediaHeartbeatEventAdStart`