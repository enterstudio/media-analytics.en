---
seo-title: Track errors on JavaScript
title: Track errors on JavaScript
uuid: 5a4fc5df-2677-4189-92af-5cd074847b39

---

# Track errors on JavaScript{#track-errors-on-javascript}

>[!IMPORTANT]
>
>The following instructions provide guidance for implementation across all 2.x SDKs. If you are implementing a 1.x version of the SDK, you can download the 1.x Developers Guides here: [Download SDKs](../../sdk-implement/download-sdks.md).

**Implement**

1. Track video player errors: 

   ```js
   onPlayerError = function() { 
       this._mediaHeartbeat.trackError("videoErrorId"); 
   };
   ```

>[!NOTE]
>
>Tracking video player errors will not stop the video tracking session. If the video player error prevents the playback from continuing, make sure that the video tracking session is closed by calling `trackSessionEnd` after calling `trackError`.

