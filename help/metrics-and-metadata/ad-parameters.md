---
seo-title: Ad parameters
title: Ad parameters
uuid: 92cd7f97-bb5a-4de6-8946-453d30271d0f
index: y
internal: n
snippet: y
---

# Ad parameters{#ad-parameters}

This topic presents a list of video ad data, including context data values, that Adobe collects via solution variables.

Table data description:

* **Label:** The name of the parameter. 
* **Implementation:** Information on implementation values and requirements

    * *Key* - Variable, set either manually in your app, or automatically by the Adobe Media SDK.
    * *Required* - Indicates whether the parameter is required for basic video tracking.
    * *Type* - Specifies the type of the variable to be set, string or number.
    * *Sent With* - Indicates when the data is sent: *Initiate* is the analytics call sent on video start, *Ad Start* is the analytics call sent on ad start, *Chapter Start* is the analytics call sent on chapter start, and *Close* is the compiled analytics call sent directly from the heartbeat server to the analytics server at the end of the media session, or the end of the ad. The Close calls are not available in network packet calls.
    * *Min. SDK Version* - Indicates which SDK version you would need to access the parameter.
    * *Sample Value* - Provides example of common variable usage.

* **Network Parameters:** Displays the values that are passed to Adobe Analytics or Heartbeat servers. This column shows the names of the parameters that are seen in the network calls generated by Adobe Media SDKs. 
* **Reporting:** Information on how to view and analyze the video data.

    * *Available* - Indicates whether the data is available in reporting by default (*Yes*), or requires custom set-up (*Custom*)
    * *Reserved Variable* - Indicates whether the data is captured as an event, eVar, prop, or classification in a reserved variable. 
    * *Report Name* - Name of Adobe Aanlytics report for variable
    * *Context Data* - Name of the Adobe Analytics context data passed to the reporting server and used in processing rules.
    * *Data Feed* - Column name for variable found in Clickstream or Live Stream data feeds
    * *Audience Manager* - Trait name found in Adobe Audience Manager

## Ad Video Data {#section_hq3_nbv_51b}

### Ad ID 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad ID** | <ul> <li> **SDK Key:** [adId](./ad-parameters.md#section_Related_APIs) </li> <li> **API Key:** `media.ad.id` </li> <li> **Required:** Yes </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `"2125"` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.name` </li> <li> **Heartbeat:** `s:asset:ad_id` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On VISIT </li> <li> **Report Name:** Ad </li> <li> **Context Data:** `a.media.ad.name` </li> <li> **Data Feed:** `videoad` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.name` </li> </ul> |

ID of the ad. (Any integer and/or letter combination) 

### Ad In Pod Position 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad In Pod Position** | <ul> <li> **SDK Key:** [position](./ad-parameters.md#section_Related_APIs) </li> <li> **API Key:** `media.ad.podPosition` </li> <li> **Required:** Yes </li> <li> **Type:** number </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `1` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.podPosition` </li> <li> **Heartbeat:** `s:asset:pod_position` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** Ad In Pod Position </li> <li> **Context Data:** `a.media.ad.podPosition` </li> <li> **Data Feed:** `videoadinpod` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.podPosition` </li> </ul> |

The position (index) of the ad inside the parent ad break. The first ad has index 0, the second ad has index 1, etc.  

### Ad Length 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Length** | <ul> <li> **SDK Key:** [length](./ad-parameters.md#section_Related_APIs) </li> <li> **API Key:** `media.ad.length` </li> <li> **Required:** Yes </li> <li> **Type:** number </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** 1.5.1 </li> <li> **Sample value:** `"15" ` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.length` </li> <li> **Heartbeat:** `l:asset:ad_length` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar and classification </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** Ad Length and Ad Length (variable) </li> <li> **Context Data:** `a.media.ad.length` </li> <li> **Data Feed:** `videoadlength` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.length` </li> </ul> |

Length of video ad in seconds.  

### Ad Player Name 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Player Name** | <ul> <li> **SDK Key:** [playerName](./ad-parameters.md#section_Related_APIs) </li> <li> **API Key:** `media.ad.playerName` </li> <li> **Required:** Yes </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `"Freewheel"` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.playerName` </li> <li> **Heartbeat:** `s:sp:player_name` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** Ad Player Name </li> <li> **Context Data:** `a.media.ad.playerName` </li> <li> **Data Feed:** `videoadplayername` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.playerName` </li> </ul> |

The name of the player responsible for rendering the ad.  

### Ad Break Name 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Break Name** | <ul> <li> **SDK Key:** [name](./ad-parameters.md#section_Related_APIs) </li> <li> **API Key:** `media.ad.podFriendlyName` </li> <li> **Required:** SDK: Yes; API: No. </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `"pre-roll"` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.podFriendlyName` </li> <li> **Heartbeat:** `s:asset:pod_name` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** Classification </li> <li> **Report Name:** Pod Name </li> <li> **Context Data:** `a.media.ad.podFriendlyName` </li> <li> **Data Feed:** `videoadpod` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.podFriendlyName` </li> </ul> |

The friendly name of the Ad Break.  

### Ad Break Index 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Break Index** | <ul> <li> **SDK Key:** [position](./ad-parameters.md#section_Related_APIs) </li> <li> **API Key:** `media.ad.podPosition` </li> <li> **Required:** Yes </li> <li> **Type:** number </li> <li> **Sent with:** </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `1` </li> </ul> | <ul> <li> **Adobe Analytics:** </li> <li> **Heartbeat:** </li> </ul> | <ul> <li> **Available:** No </li> <li> **Reserved Variable:** N/A </li> <li> **Report Name:** N/A </li> <li> **Context Data:** </li> <li> **Data Feed:** </li> <li> **Audience Manager:** </li> </ul> |

The index of the ad break inside the content starting at 1. This property is used **only** by the Media SDK to generate the Pod ID.  

### Ad Break Position 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Break Position** | <ul> <li> **SDK Key:** [startTime](./ad-parameters.md#section_Related_APIs) </li> <li> **API Key:** `media.ad.podSecond` </li> <li> **Required:** Yes </li> <li> **Type:** number </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `90` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.podSecond` </li> <li> **Heartbeat:** `l:asset:pod_offset` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** Classification </li> <li> **Report Name:** Pod Position </li> <li> **Context Data:** `a.media.ad.podSecond` </li> <li> **Data Feed:** </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.podSecond` </li> </ul> |

The offset of the ad break inside the content, in seconds.  

### Ad Break ID 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Break ID** | <ul> <li> **SDK Key:** `Automatically set` </li> <li> **API Key:** N/A </li> <li> **Required:** Yes </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `c4a577424c84067899b807c76722d495_1 ` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.pod` </li> <li> **Heartbeat:** `l:asset:pod_id` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** Ad Pod </li> <li> **Context Data:** `a.media.ad.pod` </li> <li> **Data Feed:** `videoadpod` </li> <li> **Audience Manager:** </li> </ul> |



### Ad Name 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Name** | <ul> <li> **SDK Key:** [name](./ad-parameters.md#section_Related_APIs) </li> <li> **API Key:** `media.ad.name` </li> <li> **Required:** No </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** 1.5.1 </li> <li> **Sample value:** `"Ford F-150"` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.friendlyName` </li> <li> **Heartbeat:** `s:asset:ad_name` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar and classification </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** Ad Name and Ad Name (variable) </li> <li> **Context Data:** `a.media.ad.friendlyName` </li> <li> **Data Feed:** `N/A` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.friendlyName` </li> </ul> |

Friendly name of the ad.  In reporting, "Ad Name" is the classification and "Ad Name (variable)" is the eVar.  

## Standard Ad Metadata {#section_EFB805867916411E84DE1BA5A183D86A}

### Advertiser 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Advertiser** | <ul> <li> **SDK Key:** `ADVERTISER` </li> <li> **API Key:** `media.ad.advertiser` </li> <li> **Required:** No </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** 1.5.7 </li> <li> **Sample value:** </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.advertiser` </li> <li> **Heartbeat:** `s:meta:a.media.ad.advertiser` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** <i>Advertiser </i> </li> <li> **Context Data:** `a.media.ad.advertiser` </li> <li> **Data Feed:** `videoadvertiser` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.advertiser` </li> </ul> |

Company/Brand whose product is featured in the ad.  

### Campaign ID 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Campaign ID** | <ul> <li> **SDK Key:** `CAMPAIGN_ID` </li> <li> **API Key:** `media.ad.campaignId` </li> <li> **Required:** No </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** 1.5.7 </li> <li> **Sample value:** Integer, or name (string).  </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.campaign` </li> <li> **Heartbeat:** `s:meta:a.media.ad.campaign` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** <i>Campaign ID </i> </li> <li> **Context Data:** `a.media.ad.campaign` </li> <li> **Data Feed:** `videocampaign` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.campaign` </li> </ul> |

ID of the ad campaign.  

### Creative ID 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Creative ID** | <ul> <li> **SDK Key:** `CREATIVE_ID` </li> <li> **API Key:** `media.ad.creativeId` </li> <li> **Required:** No </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** 1.5.7 </li> <li> **Sample value:** Integer, or name (string).  </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.creative` </li> <li> **Heartbeat:** `s:meta:a.media.ad.creative` </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** <i>Creative ID </i> </li> <li> **Context Data:** `a.media.ad.creative` </li> <li> **Data Feed:** `adclassificationcreative` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.creative` </li> </ul> |

ID of the ad creative.  

### Site ID 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Site ID** | <ul> <li> **SDK Key:** `SITE_ID` </li> <li> **API Key:** `media.ad.siteId` </li> <li> **Required:** No </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** 1.5.7 </li> <li> **Sample value:** </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.site` </li> <li> **Heartbeat:** `s:meta:a.media.ad.site` </li> </ul> | <ul> <li> **Available:** <i>Use custom processing rule </i> </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** <i> </i> </li> <li> **Context Data:** `a.media.ad.site` </li> <li> **Data Feed:** `N/A` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.site` </li> </ul> |

ID of the ad site.  

### Creative URL 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Creative URL** | <ul> <li> **SDK Key:** `CREATIVE_URL` </li> <li> **API Key:** `media.ad.creativeURL` </li> <li> **Required:** No </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** 1.5.7 </li> <li> **Sample value:** </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.creativeURL` </li> <li> **Heartbeat:** `s:meta:a.media.ad.creativeURL` </li> </ul> | <ul> <li> **Available:** <i>Use custom processing rule </i> </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** <i> </i> </li> <li> **Context Data:** `a.media.ad.creativeURL` </li> <li> **Data Feed:** `N/A` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.creativeURL` </li> </ul> |

URL of the ad creative.  

### Placement ID 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Placement ID** | <ul> <li> **SDK Key:** `PLACEMENT_ID` </li> <li> **API Key:** `media.ad.placementId` </li> <li> **Required:** No </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start, Ad Close </li> <li> **Min. SDK Version:** 1.5.7 </li> <li> **Sample value:** </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.placement` </li> <li> **Heartbeat:** `s:meta:a.media.ad.placement` </li> </ul> | <ul> <li> **Available:** <i>Use custom processing rule </i> </li> <li> **Reserved Variable:** eVar </li> <li> **Expiration:** On HIT </li> <li> **Report Name:** <i> </i> </li> <li> **Context Data:** `a.media.ad.placement` </li> <li> **Data Feed:** `N/A` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.placement` </li> </ul> |

Placement ID of the ad.  


## Ad Metrics {#section_22AA1565F11C4F3990E2AB51CD3213F7}

### Ad Start 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Start** | <ul> <li> **SDK Key:** Automatically set </li> <li> **API Key:** N/A </li> <li> **Required:** Yes </li> <li> **Type:** string </li> <li> **Sent with:** Ad Start </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `TRUE` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.view` </li> <li> **Heartbeat:**  `s:event:type=start`; `s:asset:type=ad`. </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** event </li> <li> **Report Name:** Ad Starts </li> <li> **Data Feed:** `videoadstart` </li> <li> **Context Data:** `a.media.ad.view` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.view` </li> </ul> |

Number of video ad starts.  

### Ad Complete 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Complete** | <ul> <li> **SDK Key:** Automatically set </li> <li> **API Key:** N/A </li> <li> **Required:** Yes </li> <li> **Type:** string </li> <li> **Sent with:** Ad Close </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `TRUE` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.complete` </li> <li> **Heartbeat:**  `s:event:type=complete`; `s:asset:type=ad`. </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** event </li> <li> **Report Name:** Ad Completes </li> <li> **Data Feed:** `videoadcomplete` </li> <li> **Context Data:** `a.media.ad.complete` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.complete` </li> </ul> |

Number of video ad completes.  

### Ad Time Spent 

| Label | Implementation | Network Parameters | Reporting |
| --- | --- | --- | --- |
| **Ad Time Spent** | <ul> <li> **SDK Key:** Automatically set </li> <li> **API Key:** N/A </li> <li> **Required:** Yes </li> <li> **Type:** string </li> <li> **Sent with:** Ad Close </li> <li> **Min. SDK Version:** Any </li> <li> **Sample value:** `15` </li> </ul> | <ul> <li> **Adobe Analytics:** `a.media.ad.timePlayed` </li> <li> **Heartbeat:** </li> </ul> | <ul> <li> **Available:** Yes </li> <li> **Reserved Variable:** event </li> <li> **Report Name:** Ad Time Spent </li> <li> **Data Feed:** `videoadtime` </li> <li> **Context Data:** `a.media.ad.timePlayed` </li> <li> **Audience Manager:** `c_contextdata.a.media.ad.timePlayed` </li> </ul> |

**Release Date: 09/13/18** The total amount of time, in seconds, spent watching the ad (i.e., the number of seconds played).  The value will be displayed in the time format (HH:MM:SS) in Analysis Workspace and Reports &amp; Analytics. In Data Feeds, Data Warehouse, and Reporting APIs the values will be displayed in seconds.  

## Related APIs {#section_Related_APIs}

`createAdObject` APIs:

* Android - [createAdObject](https://adobe-marketing-cloud.github.io/media-sdks/reference/android/com/adobe/primetime/va/simple/MediaHeartbeat.html#createAdObject-java.lang.String-java.lang.String-java.lang.Long-java.lang.Double-)
* iOS - [createAdObject](https://adobe-marketing-cloud.github.io/media-sdks/reference/ios/Classes/ADBMediaHeartbeat.html#//api/name/createAdObjectWithName:adId:position:length:)
* JavaScript - [createAdObject](https://adobe-marketing-cloud.github.io/media-sdks/reference/javascript/MediaHeartbeat.html#-static-createAdObject)

`createAdBreakObject` APIs:

* Android - [createAdBreakObject](https://adobe-marketing-cloud.github.io/media-sdks/reference/android/com/adobe/primetime/va/simple/MediaHeartbeat.html#createAdBreakObject-java.lang.String-java.lang.Long-java.lang.Double-)
* iOS - [createAdBreakObject](https://adobe-marketing-cloud.github.io/media-sdks/reference/ios/Classes/ADBMediaHeartbeat.html#//api/name/createAdBreakObjectWithName:position:startTime:)
* JavaScript - [createAdBreakObject](https://adobe-marketing-cloud.github.io/media-sdks/reference/javascript/MediaHeartbeat.html#-static-createAdBreakObject)

`MediaHeartbeatConfig` APIs:

* Android - [MediaHeartbeatConfig](https://adobe-marketing-cloud.github.io/media-sdks/reference/android/com/adobe/primetime/va/simple/MediaHeartbeatConfig.html)
* iOS - [ADBMediaHeartbeatConfig](https://adobe-marketing-cloud.github.io/media-sdks/reference/ios/Classes/ADBMediaHeartbeatConfig.html)
* JavaScript - [MediaHeartbeatConfig](https://adobe-marketing-cloud.github.io/media-sdks/reference/javascript/MediaHeartbeatConfig.html#toc0)
