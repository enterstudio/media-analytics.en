---
seo-title: Track seeking on Roku
title: Track seeking on Roku
uuid: 0572252b-397f-4aa2-b4b5-c5346b75244a

---

# Track seeking on Roku{#track-seeking-on-roku}

>[!IMPORTANT]
>
>The following instructions provide guidance for implementation across all 2.x SDKs. If you are implementing a 1.x version of the SDK, you can download the 1.x Developers Guides here: [Download SDKs](../../../sdk-implement/download-sdks.md).

**Seek tracking constants:**

|  Constant name  | Description&nbsp;&nbsp;&nbsp;&nbsp;  |
|---|---|
| `SeekStart` | Constant for tracking Seek Start event. |
| `SeekComplete` | Constant for tracking Seek Complete event. |

**Implement**

1. Listen for the playback seeking events from the media player, and on seek start event notification, track seeking using the `SeekStart` event. 

   ```
   seekContextData = {}
   seekContextData = {}
   ADBMobile().mediaTrackEvent(MEDIA_SEEK_START, seekInfo, seekContextData)
   ```

1. On seek complete notification from the media player, track the end of seeking using the `SeekComplete` event.

   ```
   seekContextData = {}
   seekContextData = {}
   ADBMobile().mediaTrackEvent(MEDIA_SEEK_COMPLETE, seekInfo, seekContextData)
   ```

See the tracking scenario [VOD playback with seeking in the main content](../../../sdk-implement/tracking-scenarios/vod-seeking.md) for more information.
