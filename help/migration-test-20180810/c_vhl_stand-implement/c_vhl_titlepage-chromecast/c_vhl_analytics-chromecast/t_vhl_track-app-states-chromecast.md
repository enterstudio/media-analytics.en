---
description: States are the different screens or views in your application. Each time a new state is displayed in your application, for example, when a user navigates from the home page to the video details screen, you should send a trackState() call.
seo-description: States are the different screens or views in your application. Each time a new state is displayed in your application, for example, when a user navigates from the home page to the video details screen, you should send a trackState() call.
seo-title: Track App States
title: Track App States
uuid: 8253c1cd-34b4-40db-b13b-f2b6127ecf88
index: y
internal: n
snippet: y
translate: y
---

# Track App States


>1. The ` trackState()` call is typically made each time a new screen is loaded.
>
>   ```
>   ADBMobile.analytics.trackState("State&amp;nbsp;Name",{});
>   ```


>   The state name is reported in the ` View State` variable in Adobe Mobile services, and a view is recorded for each ` trackState()` call. In other Analytics interfaces, ` View State` is reported as ` Page Name` and state views is reported as page views. 
>
>1. In addition to the ` State Name`, you can send additional context data with each track action call:
>
>   ```
>   var dictionary = { }; 
>   dictionary["myapp.login.LoginStatus"] = "logged in"; 
>   ADBMobile.analytics.trackState("Home Screen", dictionary); 
>   
>   ```


>   >[!IMPORTANT]
>   >
>   >Context data values must be mapped to custom variables in Adobe Mobile services.
>   States are typically viewed by using a pathing report, so you can see how users navigate your app and which states are most commonly viewed. 
>