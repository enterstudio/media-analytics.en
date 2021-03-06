---
seo-title: Test call details
title: Test call details
uuid: d3a0e62f-2fc3-413d-ac56-adbbc9b3e983

---

# Test call details{#test-call-details}

## Start the video player {#section_qts_xff_f2b}

### Video Analytics start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `pev2` | ms_s |
| `a.media.friendlyName` | Episode Title |
| `a.media.name` | 123456 |
| `a.media.length` | 120 |
| `a.media.playerName` | HTML5 |
| `a.media.view` | true |
| `a.contentType` | vod |
| `custom.[value]` | Custom metadata fields |
| `a.media.[value]` | Standard metadata fields |

**Notes:**

* Additional context data variables should be present and contain metadata. See metadata details below.
* Length for linear streams should be set to the best estimate for the current show.

### Standard metadata in Video Analytics start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `a.media.show` | Show Title |
| `a.media.season` | 6 |
| `a.media.episode` | Episode Title |
| `a.media.asset_id` | 123456 |
| `a.media.genre` | comedy |
| `a.media.first_air_date` | 2016-07-04 |
| `a.media.rating` | TV-14 |
| `a.media.originator` | production house |
| `a.media.network` | network |
| `a.media.ad_load` | 1 |
| `a.media.mvpd` | mvpd |
| `a.media.authorized` | unlocked |
| `a.media.feed` | no feed |
| `a.media.stream_format` | 0 |

### Heartbeat start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:event:type` | start |
| `l:event:playhead` | 0 |
| `l:event:duration` | 4 |
| `l:asset:name` | Episode Title |
| `l:asset:video_id` | 123456 |
| `l:asset:length` | 120 |
| `l:stream:type` | vod |
| `s:asset:type` | main |
| `s:meta:custom.[value]` | Custom metadata fields |
| `s:meta:a.media.[value]` | Standard metadata fields |

### Video metadata in Video Analytics start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `custom.metadataA` | value |
| `custom.metadataB` | value |

**Notes:**

* Additional context data variables should be present and contain metadata. See metadata details below.
* Playhead position for linear streams on video start should be set to the seconds elapsed since the start of the current show, not 0.

### Heartbeat Analytics start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:event:type` | aa_start |
| `l:event:playhead` | 0 |
| `l:event:duration` | 4 |
| `l:asset:name` | Episode Title |
| `l:asset:video_id` | 123456 |
| `l:asset:length` | 120 |
| `l:stream:type` | vod |
| `s:asset:type` | main |

### Video metadata in Heartbeat start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:meta:custom.metadata` | value |
| `s:meta:custom.metadata` | value |

### Standard metadata in Heartbeat start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:meta:a.media.show` | Show |
| `s:meta:a.media.season` | 6 |
| `s:meta:a.media.episode` | Episode Title |
| `s:meta:a.media.asset_id` | 123456 |
| `s:meta:a.media.genre` | comedy |
| `s:meta:a.media.first_air_date` | 2018-07-04 |
| `s:meta:a.media.rating` | TV-14 |
| `s:meta:a.media.originator` | production house |
| `s:meta:a.media.network` | network |
| `s:meta:a.media.ad_load` | 1 |
| `s:meta:a.media.mvpd` | mvpd |
| `s:meta:a.media.authorized` | unlocked |
| `s:meta:a.media.feed` | no feed |
| `s:meta:a.media.stream_format` | 0 |

**Notes:**

* This call indicates that the heartbeat library has requested that an analytics pev2=ms_s call be sent to the analytics server.
* This call does not contain custom metadata.

## View ad playback {#section_wz3_yff_f2b}

### Video Analytics ad start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `pev2` | msa_s |
| `a.media.name` | 123456 |
| `a.media.ad.name` | 9378 |
| `a.media.ad.friendlyName` | Video_VPAID_DFA |
| `a.media.ad.podFriendlyName` | preroll |
| `a.media.ad.length` | 15 |
| `a.media.ad.playerName` | HTML5 |
| `a.media.ad.pod` | c27aaf3ff8224bb6b9ebfe1b2e79073d_1 |
| `a.media.ad.podPosition` | 1 |
| `a.media.ad.podSecond` | 0.0 |
| `a.media.ad.view` | True |
| `custom.[value]` | Metadata fields |
| `a.media.[value]` | Standard metadata fields |

**Note:** Additional context data variables should be present and contain metadata. See metadata details below.

### Heartbeat ad start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:event:type` | start |
| `l:event:playhead` | 0 |
| `l:event:duration` | 4 |
| `l:asset:ad_id` | 9378 |
| `l:asset:length` | 120 |
| `l:stream:type` | vod |
| `s:asset:type` | ad |
| `s:meta:custom.[value]` | Custom metadata fields |
| `s:meta:a.media.[value]` | Standard metadata fields |

### Video metadata in Video Analytics ad start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `custom.metadata` | value |
| `custom.metadata` | value |

### Standard metadata in Video Analytics ad start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `a.media.show` | Show Title |
| `a.media.season` | 6 |
| `a.media.episode` | Episode Title |
| `a.media.asset_id` | 123456 |
| `a.media.genre` | comedy |
| `a.media.first_air_date` | 2016-07-04 |
| `a.media.rating` | TV-14 |
| `a.media.originator` | production house |
| `a.media.network` | network |
| `a.media.ad_load` | 1 |
| `a.media.mvpd` | mvpd |
| `a.media.authorized` | unlocked |
| `a.media.feed` | no feed |
| `a.media.stream_format` | 0 |

**Notes:**

* Additional context data variables should be present and contain metadata. See metadata details below.
* Ad length may be set to -1 if not available on ad start.

### Heartbeat Analytics ad start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:event:type` | aa_ad_start |
| `l:event:playhead` | 0 |
| `l:event:duration` | 0 |
| `l:asset:ad_id` | 9378 |
| `l:asset:ad_length` | 15 |
| `l:stream:type` | vod |
| `s:asset:type` | ad |

### Video metadata in Heartbeat ad start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:meta:custom.metadata` | value |
| `s:meta:custom.metadata` | value |

### Standard metadata in Heartbeat ad start call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:meta:a.media.show` | Show |
| `s:meta:a.media.season` | 6 |
| `s:meta:a.media.episode` | Episode Title |
| `s:meta:a.media.asset_id` | 123456 |
| `s:meta:a.media.genre` | comedy |
| `s:meta:a.media.first_air_date` | 2018-07-04 |
| `s:meta:a.media.rating` | TV-14 |
| `s:meta:a.media.originator` | production house |
| `s:meta:a.media.network` | network |
| `s:meta:a.media.ad_load` | 1 |
| `s:meta:a.media.mvpd` | mvpd |
| `s:meta:a.media.authorized` | unlocked |
| `s:meta:a.media.feed` | no feed |
| `s:meta:a.media.stream_format` | 0 |

**Notes:**

* Additional context data variables should be present and contain metadata. See metadata details below.
* Ad length may be set to -1 if not available on ad start.

### Heartbeat ad complete call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:event:type` | complete |
| `l:event:playhead` | 15 |
| `l:event:duration` | 0 |
| `l:asset:ad_id` | 9378 |
| `l:asset:ad_length` | 15 |
| `l:stream:type` | vod |
| `s:asset:type` | ad |

### Heartbeat ad play call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:event:type` | play |
| `l:event:playhead` | 15 |
| `l:event:duration` | 0 |
| `l:asset:ad_id` | 9378 |
| `l:asset:ad_length` | 15 |
| `l:stream:type` | vod |
| `s:asset:type` | ad |

## Play main content {#section_u1l_1gf_f2b}

### Heartbeat play call

|  Parameter | Value (sample)&nbsp;&nbsp; |
|---|---|
| `s:event:type` | play |
| `l:event:playhead` | 29 |
| `l:event:duration` | 10189 |
| `l:asset:name` | Episode Title |
| `l:asset:video_id` | 123456 |
| `l:asset:length` | 120 |
| `l:stream:type` | vod |
| `s:asset:type` | main |

**Notes:**

* The playhead position should increment by 10 with every play call.
* The `l:event:duration` value represents the number of milliseconds since the last tracking call and should be roughly the same value on each 10 second call.

