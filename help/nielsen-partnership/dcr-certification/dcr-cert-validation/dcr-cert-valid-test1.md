---
seo-title: Test 1  Standard playback
title: Test 1  Standard playback
uuid: 530477b8-4de3-449d-bb6d-a47dadd1da5a

---

# Test 1: Standard playback{#test-standard-playback}

This test case is required as part of the certification request form and validates general playback and sequencing.

Download the certification request form here: [Certification request form](../../../nielsen-partnership/dcr-certification/dcr-cert-request-form.md).

Video implementations are composed of the following types of tracking calls:

* Video and Ad Start calls are sent directly to the AppMeasurement server. 
* Video Analytics (VA) heartbeat calls are sent on start and every ten seconds to the Adobe VA tracking server. 
* Nielsen DCR calls are sent on start and every five minutes to the Nielsen tracking server.

Video tracking behaves the same across desktop, OTT, and mobile.

You must complete and record these tasks in the following order:

1. **Load the page or app.**

   **Tracking Servers** (For all website and mobile apps):

   * **AppMeasurement (Adobe Analytics) -** An RDC tracking server or CNAME that resolves to an RDC server is required for the Experience Cloud Visitor ID service. The analytics tracking server should end in `.sc.omtrdc.net` or be a CNAME.     
   * **Video Analytics (Heartbeats) -** This server always has the format `[namespace].hb.omtrdc.net`, where `[namespace]` is defined by your login company and is provided by Adobe.
   * **Nielsen -** Unless specified by Nielsen, this server will always be `secure-dcr.imrworldwide.com`.

   You need to validate certain key, universal variables across all tracking calls:

   * **ADOBE**

     **Adobe Visitor ID (`mid`):** The `mid` variable is used to capture the value set in the AMCV cookie. The `mid` variable is the primary identification value for both websites and mobile apps, and also indicates that the Experience Cloud Visitor ID service is set-up properly. It is found in both AppMeasurement and Video Analytics (VA) calls.

     **Heartbeat Play Call**

     |  Parameter | Value (sample) |
     |---|---|
     | `s:event:type` | play |
     | `s:user:mid` | 30250035503789876473484580554595324209 |

     **Video Analytics Start Call**

     |  Parameter | Value (sample) |
     |---|---|
     | `pev2` | ms_s |
     | `mid` | 30250035503789876473484580554595324209 |

     **Website Page Call**

     |  Parameter | Value (sample) |
     |---|---|
     | `mid` | 30250035503789876473484580554595324209 |

     **Lifecycle Call**

     |  Parameter | Value (sample) |
     |---|---|
     | `pev2` | ADBINTERNAL:Lifecycle |
     | `mid` | 30250035503789876473484580554595324209 |

     >[!NOTE]
     >
     >On VA Start Calls ( `s:event:type=start`) the `mid` values may not be present. This is OK. They may not appear until the VA Play Calls ( `s:event:type=play`).

   * **NIELSEN**

     **Nielsen Client ID:** The Nielsen Client ID value is used to correctly identify the Nielsen account to be credited with the viewer data.

     **Nielsen Start Call**

     |  Parameter | Value (sample) |
     |---|---|
     | `st` | dcr |
     | `ci` | us-123456 |

     **Heartbeat Start Call**

     |  Parameter | Value (sample) |
     |---|---|
     | `s:event:type` | start |
     | `s:meta:a.nielsen.clientid` | us-123456 |

     **VA Start Call**

     |  Parameter | Value (sample) |
     |---|---|
     | `pev2` | ms_s |
     | `a.nielsen.clientid` | us-123456 |

1. **Start the video player.** When the video player starts, the key calls are sent in the following order:

   1. Video analytics start&#42; 
   1. Heartbeat start&#42; 
   1. Heartbeat analytics start 
   1. Nielsen view ping

   &#42;These calls contain additional metadata and Nielsen variables. For call parameters and metadata, see [Test call details](../../../nielsen-partnership/dcr-certification/dcr-cert-validation/dcr-cert-valid-call-details.md).

1. **View ad break if available.**

   * **Ad Start**

     When the video ad starts, the following key calls are sent in the following order:

     1. Video ad analytics start&#42; 
     1. Heartbeat ad start&#42; 
     1. Heartbeat ad analytics start 
     1. Nielsen DCR view ping

     &#42;These calls contain additional metadata and Nielsen variables. For call parameters and metadata, see [Test call details](../../../nielsen-partnership/dcr-certification/dcr-cert-validation/dcr-cert-valid-call-details.md).

   * **Ad Play**

     During ad playback, Heartbeat calls are sent to the Heartbeat server every second. 
    
   * **Ad Complete**

     There should be a Nielsen DCR ping. At the 100% point on a video ad, a Heartbeat complete call will be sent.

1. **Pause ad playback for 30 seconds, if available.** 

   **Ad Pause**

   During ad pause, Heartbeat calls are sent to the Heartbeat server every second.

   >[!NOTE]
   >
   >The playhead value should remain constant during the pause.

1. **Play main content video for 10 minutes uninterrupted.**

   **Content Play**

   During regular main content playback, Heartbeat calls are sent to the Heartbeat server every ten seconds. Nielsen calls are sent to the Nielsen server every five minutes.

   **Notes:**

   * The playhead position should increment by 10 with every play call.
   * The `l:event:duration` value represents the number of milliseconds since the last tracking call and should be roughly the same value on each 10 second call.

   For call parameters and metadata, see [Test call details](../../../nielsen-partnership/dcr-certification/dcr-cert-validation/dcr-cert-valid-call-details.md).

1. **Pause during playback for at least 30 seconds.**

   On pause of the video player, pause event calls will be sent every 10 seconds. After pause ends the play events should resume. 

1. **Seek/scrub video.**

   On scrubbing of video playhead, no special tracking calls are sent, however, when video playback resumes after scrubbing the playhead value should reflect the new position within the main content. 

1. **Replay video (VOD only).**

   When a video is replayed, a new set of video start calls should be sent, as if this is a fresh video view. 

1. **View next video in playlist.**

   On video start of the next video in a playlist, a new set of video start calls should be sent. 

1. **Switch video or stream.**

   When switching live streams, a Heartbeat complete call for the first stream should not be sent. The video start calls and video play calls should begin with the new show and stream name and with the correct playhead and duration values for the new show.

