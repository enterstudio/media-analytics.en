---
description: You can use these methods to send signals and retrieve visitor segments from Audience Manager.
seo-description: You can use these methods to send signals and retrieve visitor segments from Audience Manager.
seo-title: Audience Manager Methods
title: Audience Manager Methods
uuid: 1ff6847c-f181-40c8-a621-37245cb6438c
index: y
internal: n
snippet: y
translate: y
---

# Audience Manager Methods



<table id="table_0DD1B40D95624AF6AB53622F8DDCDEFA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> audienceVisitorProfile</span> </p> </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. Returns an empty object if no signal has been submitted yet. </p> <p> 
     <codeblock>
       ADBMobile().audienceVisitorProfile()
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> audienceDpid</span> </p> </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. Returns an empty obje t if no signal has been submitted yet. </p> <p> 
     <codeblock>
       ADBMobile().audienceDpid()
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> audienceDpuuid</span> </p> </td> 
   <td colname="col2"> <p>Returns the current DPUUID. </p> <p> 
     <codeblock>
       ADBMobile().audienceDpuuid()
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> audienceSetDpidAndDpuuid</span> </p> </td> 
   <td colname="col2"> <p>Sets the DPID and DPUUID. If DPID and DPUUID are set, they will be sent with each signal. </p> <p> 
     <codeblock>
      ADBMobile().audienceSetDpidAndDpuuid("myDpid",
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"myDpuuid")
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> audienceSubmitSignal</span> </p> </td> 
   <td colname="col2"> <p>Sends audience management a signal with traits. </p> <p> 
     <codeblock>
       ADBMobile().audienceSubmitSignal()
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>
