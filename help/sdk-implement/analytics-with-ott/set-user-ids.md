---
seo-title: Set user IDs
title: Set user IDs
uuid: fdd54fec-79cd-4bf8-b17e-4d61d84f6310

---

# Set user IDs{#set-user-ids}

The user ID is a unique custom visitor identifier defined by the application for a user.

Set and get the unique user ID on the ADBMobile SDK as follows:

1. **Set:**

   * **Roku:** 
   
     ```    
     ADBMobile().setUserIdentifer("app-generated-unique-id")
     ```
   
   * **Chromecast:** 
   
     ```    
     ADBMobile().config.setUserIdentifer("app-generated-unique-id");
     ```

1. **Get:**

   * **Roku:** 
   
     ```    
     vid = ADBMobile().userIdentifer()
     ```
   
   * **Chromecast:** 
   
     ```    
     vid = ADBMobile().config.getUserIdentifer();
     ```
