---
description: null
seo-description: null
seo-title: Retrieving Stored Identifiers
title: Retrieving Stored Identifiers
uuid: a7e5487d-887c-46f7-9584-86807f5a6463
index: y
internal: n
snippet: y
translate: y
---

# Retrieving Stored Identifiers

This information helps you retrieve locally stored user identities from your Chromecast app.


>[!IMPORTANT]
>
>The ` getAllIdentifiersAsync()` method retrieves all user identities known and persisted by the Chromecast SDK. You must call this method **before** a user opts-out.



The locally stored identities are returned in a JSON string, which might contain: 

* Company Context - IMS Org IDs
* User IDs
* Experience Cloud ID (MCID)
* Data Source IDs (DPID, DPUUID)
* Analytics IDs (AVID, AID, VID, and associated RSIDs)
* Audience Manager ID (UUID)
For example: 
```
ADBMobile.config.getAllIdentifiersAsync(callback)
```
