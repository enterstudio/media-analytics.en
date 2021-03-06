---
seo-title: Overview
title: Overview
uuid: 4d73c47f-d0a4-4228-9040-d6432311c9eb

---

# Overview{#overview}

>[!IMPORTANT]
>
>The following instructions provide guidance for implementation across all 2.x SDKs. If you are implementing a 1.x version of the SDK, you can download the 1.x Developers Guides here: [Download SDKs](../../sdk-implement/download-sdks.md).

Quality of experience tracking includes quality of service (QoS) and error tracking, both are optional elements and are **not** required for core video heartbeat implementations. You can use the video player API to identify the variables related to QoS and error tracking. Here are the key elements of tracking quality of experience:

**On any QoS metric changes:**

Create or update the QoS object instance for the playback.

**On all bitrate change events**:

* Call `trackEvent(Media.Heartbeat.Event.BitrateChange);`

## Implement {#section_3B8EBEB167624D0481E8AF4761F83047}

1. Identify when any of QOS metrics change during video playback, create the `MediaObject` using the QoS information, and update the new QoS information.

   **QoSObject variables:** 

   >[!TIP]
   >
   >These variables are only required if you are planning to track QoS.

   | Variable | Description | Required |
   | --- | --- | :---: |
   | `bitrate` | Current bitrate | Yes |
   | `startupTime` | Startup time | Yes |
   | `fps` | FPS value | Yes |
   | `droppedFrames` | Number of dropped frames | Yes |

1. Make sure that `getQoSObject()` method returns the most updated QoS information. 
1. When playback switches bitrates, call the `BitrateChange` event in the Media Heartbeat instance.

   >[!IMPORTANT]
   >
   >Update the QoS object and call the bitrate change event on every bitrate change. This provides the most accurate QoS data.

The following sample code uses the JavaScript 2.x SDK for an HTML5 video player. You should use this code with the core video playback code. 

```js
var mediaDelegate = new MediaHeartbeatDelegate(); 
 
...  
 
// This is called periodically by MediaHeartbeat instance 
mediaDelegate.prototype.getQoSObject = function() { 
    return this.qosInfo; 
}; 
 
if (e.type == "qos_update") { 
    var qosInfo = MediaHeartbeat.createQoSObjectt(<BITRATE>,<STARTUP_TIME>,<FPS>,<DROPPED_FRAMES>); 
    mediaDelegate.qosInfo = qosInfo; 
}; 
 
if (e.type == "bitrate_change") { 
    this.mediaHeartbeat.trackEvent(MediaHeartbeat.Event.BitrateChange, qosObject); 
};
```

## Validate {#section_F3174831408947A893F7E8C15659E5AA}

**Bitrate change**

On each bitrate change, a Heartbeat `bitrate_change` call will be sent.

**Error**

On player error, a Heartbeat error call will be sent with the error value included. 
