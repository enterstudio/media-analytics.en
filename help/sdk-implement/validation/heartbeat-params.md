---
seo-title: Heartbeat parameter descriptions
title: Heartbeat parameter descriptions
uuid: e9ddda32-0952-43d0-a702-49f5b1bfd8cf

---

# Heartbeat parameter descriptions{#heartbeat-parameter-descriptions}

List of heartbeat parameters that Adobe collects and processes on the heartbeats server:

## All Events

| Name | Required / Optional | Data Source | Description&nbsp;&nbsp; |
| ---  | :---: | --- | --- |
| `s:event:type` | R | Media SDK | The type of the event being tracked. Event types: <ul> <li> `s:event:type=start` </li> <li> `s:event:type=complete` </li> <li> `s:event:type=chapter_start` </li> <li> `s:event:type=chapter_complete` </li> <li> `s:event:type=buffer` </li> <li> `s:event:type=pause` </li> <li> `s:event:type=resume` </li> <li> `s:event:type=bitrate_change` </li> <li> `s:event:type=aa_start` </li> <li> `s:event:type=stall` </li> <li> `s:event:type=end` </li> </ul> |
| `l:event:prev_ts` | R | Media SDK | The timestamp of the last event of the same type in this session. The value is `-1` |
| `l:event:ts` | R | Media SDK | The timestamp of the event.  |
| `l:event:duration` | R | Media SDK | This value is set internally (in milliseconds) by the VHL Library, not by the player. It is used to compute the time spent metrics on the backend. For example `a.media.totalTimePlayed` `type=play` Note:  For some of the HB that are sent This parameter is set to 0 for certain events because they are "state change events" (e.g., `type=complete` `type=chapter_complete` `type=bitrate_change` |
| `l:event:playhead` | R | `VideoInfo` | The playhead was inside the currently active asset (main or ad), when the event was recorded.  |
| `s:event:sid` | R | Media SDK | The session ID (a randomly generated string). All events in a certain session (video + ads) should be the same.  |
| `l:asset:duration / l:asset:length` (Renamed from `length` `duration` | R | `VideoInfo` | The video asset length of the main asset.  |
|  `s:asset:publisher` | R | `MediaHeartbeatConfig` | The publisher of the asset.  |
|  `s:asset:video_id` | R | `VideoInfo` | An ID uniquely identifying the video in the publisher's catalog.  |
| `s:asset:type` | R | Media SDK | The asset type (main or ad).  |
| `s:stream:type` | R | `VideoInfo` | The stream type. Can be one of the following: <ul> <li> `live` </li> <li> `vod` </li> <li> `linear` </li> </ul>.  |
| `s:user:id` | O | Config object for mobile, app measurement VisitorID | User's specifically set Visitor ID.  |
| `s:user:aid` | O | Experience Cloud Org | The user's analytics Visitor ID value.  |
| `s:user:mid` | R | Experience Cloud Org | The user's Experience cloud visitor ID value.  |
| `s:cuser:customer_user_ids_x` | O | `MediaHeartbeatConfig` | All customer user IDs set on Audience Manager.  |
| `l:aam:loc_hint` | R | `MediaHeartbeatConfig` | AAM data sent on each payload after `aa_start` |
| `s:aam:blob` | R | `MediaHeartbeatConfig` | AAM data sent on each payload after `aa_start` |
| `s:sc:rsid` | R | Report Suit ID (or IDs) | SiteCatalyst RSID where reports should be sent.  |
| `s:sc:tracking_server` | R | `MediaHeartbeatConfig` | SiteCatalyst tracking server.  |
| `h:sc:ssl` | R | `MediaHeartbeatConfig` | Whether the traffic is over HTTPS (if set to 1) or over HTTP (is set to 0).  |
| `s:sp:ovp` | O | `MediaHeartbeatConfig` | Set to "primetime" for Primetime players, or the actual OVP for other players.  |
| `s:sp:sdk` | R | `MediaHeartbeatConfig` | The OVP version string.  |
| `s:sp:player_name` | R | `VideoInfo` | Video player name (the actual player software, used to identify the player).  |
| `s:sp:channel` | O | `MediaHeartbeatConfig` | The channel where the user is watching the content. For a mobile app, the app name. For a website, the domain name.  |
| `s:sp:hb_version` | R | Media SDK | The version number of the VideoHeartbeat library issuing the call.  |
| `l:stream:bitrate` | R | `QoSInfo` | The current value of the stream bitrate (in bps).  |

## Error Events

| Name | Required / Optional | Data Source | Description&nbsp;&nbsp; |
| ---  | :---: | --- | --- |
| `s:event:source` | R | Media SDK | The source of the error, either player-internal, or the application-level.  |
| `s:event:id` | R | Media SDK | Error ID, uniquely identifies the error.  |

## Ad Events

| Name | Required / Optional | Data Source | Description&nbsp;&nbsp; |
| ---  | :---: | --- | --- |
| `s:asset:ad_id` | R | `AdInfo` | The name of the ad.  |
| `s:asset:ad_sid` | R | Media SDK | A unique identifier generated by the Media SDK, appended to all ad-related pings.  |
| `s:asset:pod_id` | R | Media SDK | Pod ID inside the video. This value is computed automatically based on the following formula: `MD5(video_id) + "_" + [pod index]` |
| `s:asset:pod_position` | R | `AdBreakInfo` | Index of the ad inside the pod (the first ad has index 0, the second ad has index 1, etc.).  |
| `s:asset:resolver` | R | `AdBreakInfo` | The ad resolver.  |
| `s:meta:custom_ad_metadata.x` | O | `MediaHeartbeat` | The custom ad metadata.  |

## Chapter Events

| Name | Required / Optional | Data Source | Description&nbsp;&nbsp; |
| ---  | :---: | --- | --- |
| `s:stream:chapter_sid` | R | Media SDK | The unique identifier associated to the playback instance of the chapter.  Note: A chapter can be played multiple times due to seek-back operations performed by the user.  |
| `s:stream:chapter_name` | O | `ChapterInfo` | The chapter's friendly (i.e., human readable) name.  |
| `s:stream:chapter_id` | R | Media SDK | The unique ID of the chapter. This value is computed automatically based on the following formula: `MD5(video_id) + "_" + chapter_pos` |
| `l:stream:chapter_pos` | R | `ChapterInfo` | The chapter's index in the list of chapters (starting with 1).  |
| `l:stream:chapter_offset` | R | `ChapterInfo` | The chapter's offset (expressed in seconds) inside the main content, excluding ads.  |
| `l:stream:chapter_length` | R | `ChapterInfo` | The chapter's duration (expressed in seconds).  | 
| `s:meta:custom_chapter_metadata.x` | O | `ChapterInfo` | Custom chapter metadata.  |

## Session End Event

| Name | Required / Optional | Data Source | Description&nbsp;&nbsp; |
| ---  | :---: | --- | --- |
| `s:event:type=end` | R | Media SDK | The `end` `close` | 

