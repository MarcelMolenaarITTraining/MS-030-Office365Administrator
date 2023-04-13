
## Module 8 - Lab 8 - Exercise 1 - Configure Microsoft Teams

In this exercise you will learn how to manage and configure Microsoft Teams through the Teams admin center. As Holly Dickson, Adatum's Enterprise Admin, you have decided to customize the company's Global meeting policy. Meeting policies control the features that are available to participants in meetings that are scheduled by users in an organization. An organization-wide policy named Global is created by default, and all users within the organization are automatically assigned this meeting policy. An admin can either make changes to this policy or create one or more custom policies and assign users to them. Holly has chosen to customize the Global policy.

Holly also wants to use the Teams meetings settings to control whether anonymous users can join Teams meetings and customize meeting invitations. As part of Adatum’s pilot project for implementing Microsoft Teams, she has been tasked with configuring Teams meeting settings to see how they handle email invitations.

Next, Holly wants to create a new messaging policy that addresses the chat and channel messaging requirements set forth by Adatum’s project team. She will then create a resource account for a cloud call queue, which is a service that accepts customer calls, plays a greeting message, and then places the customer calls in a wait queue while searching a pre-configured list of agents to answer each call. Once she has created the resource account for her calling queue, she will create the call queue itself and assign it the resource account.

At this point, Holly will turn her attention to calling policies. She has been tasked with creating a custom calling policy for Adatum. Instead of customizing the default global policy, she will follow best practice guidelines and create her own customized policy that will be used as Adatum’s default policy.

Finally, Holly wants to manage Teams access, and specifically external access and guess access. She wants to block communication with users from a specific domain  that has been the source of multiple spam attacks within Adatum over the past year. At the same time, she wants to allow communication with the users from another domain that is one of Adatum's key business partners.



### Task 1 – Manage Global Meeting Policy

Meeting policies control the features that are available to participants in meetings that are scheduled by users in your organization. An organization-wide policy named Global is created by default, and all users in your organization are automatically assigned this meeting policy. You can either make changes to this policy or create one or more custom policies and assign users to them. When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign the policy to one or more users who will have the settings applied to them. 

As Holly Dickson, Adatum's Enterprise Administrator, you want to customize the company's Global meeting policy as part of Adatum’s pilot project for implementing Microsoft Teams.

1. Switch to **LON-DC1**, where you should still be logged in as **ADATUM\Administrator** and password **Pa55w.rd**.

2. You should still have Microsoft Edge and the Microsoft 365 admin center open from an earlier lab. If so, proceed to the next step; otherwise, open Microsoft Edge, navigate to **https://portal.office.com/**, log in as **Holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is the tenant ID provided by your lab hosting provider) with a password of **Pa55w.rd**, and then in the **Microsoft Office Home** page, select **Admin** to open the Microsoft 365 admin center.

3. To start fresh in this Teams lab exercise, close any tab in the Edge browser other than the **Microsoft Office Home** tab and the **Microsoft 365 admin center** tab. 

4. In the **Microsoft 365 admin center** tab, in the left-hand navigation pane, select **Show all** (if necessary), then scroll down to **Admin centers** and select **Teams.** This will open the **Microsoft Teams admin center** in a new tab.

5. If a **Welcome to the Teams admin center** window appears, select the **Skip tour** option.

5. In the **Microsoft Teams admin center**,  in the left-hand navigation pane, select **Meetings** and then select **Meeting policies**.

6. In the **Meeting policies** window, scroll down to the list of meeting policies and select **Global (Org-wide default)**. 

7. In the **Global** window that appears, under the **General** section, review each setting. All settings in this section should be turned **On**.

8. Under the **Audio &amp; video** section, review each setting. Set **Allow transcription** to **On**.

9. Under the **Content Sharing** section, review each setting. Select the drop-down arrow in the **Screen sharing mode** field and select **Single application** and then set the **Allow an external participant to give or request control** setting to **On**.

10. Under the **Participants &amp; guests** section, review each setting. Because Adatum has had issues in the past with non-invited external users dialing into meetings, you have been asked to set the **Allow dial-in users to bypass the lobby** option to **Off**. This setting controls whether people who dial in by phone will automatically join the meeting or must wait in the lobby until they are admitted to the call. Because the **Automatically admit people** setting is set to **Everyone in your organization**, anyone who dials-in will wait in the lobby until admitted; this includes both Adatum and non-Adatum participants. You may decide to turn this setting **On** if it proves to be problematic in practice, but for now, you want to begin with this level of control. 

11. Select the **Save** button at the bottom of the page.

12. Leave all tabs open in your browser and proceed to the next task. 


### Task 2 – Manage Meeting Settings

As Holly Dickson, Adatum’s Microsoft 365 Enterprise Administrator, you use the Teams meetings settings to control whether anonymous users can join Teams meetings and customize meeting invitations. You can also use these settings to enable Quality of Service (QoS) and set port ranges for real-time traffic. These settings apply to all Teams meetings that users schedule in your organization. As part of Adatum’s pilot project for implementing Microsoft Teams, you want to configure Teams meeting settings to see how they handle email invitations.

1. On **LON-DC1** you should still have the **Microsoft Teams admin center** open from the prior task. In the left-hand navigation pane, under the **Meetings** group, select **Meeting settings.**

2. On the **Meetings settings** page, under the **Email invitation** section, enter (or copy and paste in) the following information:

	- Logo URL: leave blank

	- Legal URL: **https://adatum.com/legal.html**

	- Help URL: **https://adatum.com/joiningmeetinghelp.html**

	- Footer: **Please accept at your earliest convenience. Thank you!**

3. Select the **Preview invite** button.

4. On the **Email invite preview** window, review the preview image of the invitation and then select the **Close** button at the bottom of the page.

5. On the **Meetings settings** page, under the **Network** section, review the current settings.  

	‎**Note:** If you have specific ports that your company uses for sending and receiving media traffic, this is where you would enter those ports. If you do not have specific media ports prescribed by your network administrator, then you would leave this section alone. For the purposes of this lab, you will not update this section. 

6. Scroll to the bottom of the page and select **Save**.

7. Leave all tabs open in your browser and proceed to the next task. 


### Task 3 – Manage Messaging Policies

Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams. You can use the Global default policy that is created automatically or create one or more custom messaging policies for people in your organization. After you create a policy, you can assign it to a user or group of users in your organization. 

As part of her Microsoft Teams pilot project for Adatum, Holly wants to create a new messaging policy that addresses the chat and channel messaging requirements set forth by Adatum’s project team. 

1. On **LON-DC1** you should still have the **Microsoft Teams admin center** open from the prior task. In the left-hand navigation pane, select **Messaging policies**.

2. In the **Messaging policies** window, view the list of messaging policies. As you can see, only the **Global (Org-wide default)** policy exists. Select **+Add** in the menu bar that appears above the list of policies.

3. In the **Messaging policies\Add** window, enter **Chat and Channel Messaging Policy** in the **New messaging policy** field at the top of the form.

4. Select the following values for each setting:

	- Owners can delete sent messages: **Off**

	- Delete sent messages: **Off**

	- Edit sent messages: **On**

	- Read receipts: **Turned on for everyone**

	- Chat: **On** 

	- Use Giphy in conversations: **Off**

	- Giphy content rating: **Strict**

	- Use Memes in conversations: **Off**

	- User Stickers in conversations: **Off**

	- Allow URL previews: **On**

	- Translate messages: **On**

	- Allow immersive reader for viewing messages: **On**

	- Send urgent messages using priority notifications: **On** 

	- Create voice messages: **Allowed in chats and channels**

	- On mobile devices, display favorite channels about recent chats: **Disabled**

	- Remove users from a group chat: **Off**

	- Suggested replies: **On**

5. Select **Save.** 

6. Leave all tabs open in your browser and proceed to the next task. 


### Task 4 – Create a Resource Account

A resource account, which is referred to as a disabled user object in Azure Active Directory, can be used to represent resources in general. For example, a resource account in Exchange can be used to represent conference rooms, and in Microsoft Teams, resource accounts can be used to represent Phone System call queues and auto attendants. 

As part of Adatum’s pilot project for implementing Microsoft Teams, Holly Dickson has been asked to create a resource account for a cloud call queue, which is a service that accepts customer calls, plays a greeting message, and then places the customer calls in a wait queue while searching a pre-configured list of agents to answer each call. 

Creating a calling queue is a two-step process. In this task, you will first create a resource account that represents the call queue. In the next task, you will create the actual call queue and associate it with this resource account. 

1. On **LON-DC1** you should still have the **Microsoft Teams admin center** open from the prior task. In the left-hand navigation pane, select **Org-wide Settings** and then select **Resource accounts.**

2. In the **Resource accounts** window, select **+Add** in the menu bar at the top of the page.

3. In the **Add resource account** pane that appears on the right, enter the following information:

	- Display name: **Calling Queue 1**

	- Username: **CQ1**

	- Domain name: In the domain name field to the right of the username, select the drop-down arrow and select **M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider)

	- Resource account type: **Call queue**

4. Select **Save**. **Calling Queue 1** will now appear in the list of Resource accounts. 

5. Leave all tabs open in your browser and proceed to the next task. 


### Task 5 - Create a Call Queue

Now that you have created the resource account for your calling queue, you will create the call queue itself and assign it the resource account.

1. On **LON-DC1** you should still have the **Microsoft Teams admin center** open from the prior task. In the left-hand navigation pane, select **Voice** and then select **Call queues.**

2. In the **Call queues** window, select **+Add** in the menu bar at the top of the page.

3. In the **Call queues\Add** window, enter **Call Queue 1** in the **Call queue name** field at the top of the form.

4. The page displays a message indicating **You haven’t added any resource accounts yet.** Below this message, select the **Add accounts** button.

5. In the **Add account** pane that appears on the right-side of the screen, in the **Search for resource accounts you want to add** box, enter **Calling.** As you type **Calling**, a window appears listing call resource accounts whose title starts with **Calling**. **Calling Queue 1** is displayed. As you hover your mouse over **Calling Queue 1**, an **Add** button appears to the right of it. Select the **Add** button.

6. At the bottom of the **Add accounts** pane, select **Add.** This returns you to the **Call Queue 1** window, which now displays **Calling Queue 1** in the list of Resource accounts associated with this call queue.

7. In the **Call Queue 1** window, scroll down the page and select the following values for each option:

	- Greeting: **No greeting**

	- Music on hold: **Play default music**

	- Call answering: 
	
		- **Choose which call agents to associate with this call queue:** Select the **Add users** button. In the **Add users** pane that appears on the right-side of the screen, in the **Add a user or users** box, enter **Allan**. As you type **Allan**, a window appears listing users whose name starts with **Allan**. As you hover your mouse over **Allan Deyoung**, an **Add** button appears to the right of it. Select the **Add** button.
		
		**Important:** Note the red error message that appears across the top of the page. The error message indicates that Allan cannot be associated with this call queue because he is not enterprise-voice enabled. In the **Add users** window, select **Cancel**. In the red error message, select the **X** on the right side of the error message to close it. 
		
		- **Choose which groups to associate with this call queue:** Select the **Add groups** button. In the **Add call agents** pane on the right-side of the screen, in the **Add distribution lists or groups** box, enter **Sales.** As you type Sales, a window appears listing the groups whose name starts with Sales. As you hover your mouse over **Sales Department**, an **Add** button appears to the right of it. Select the **Add** button.
		
		In the **Add call agents** pane, the Sales Department appears under **Selected groups**. Select the **Add** button at the bottom of the pane.

		- Routing Method: **Round Robin**   
		
		- Presence-based routing - **Off**
	
		- Agents can opt out of taking calls: **On**
		
		- Agent alert time (in seconds) - 45 (entering the value in the field is easier than dragging the slider icon)

	- Call overflow handling: **leave all settings to their default values**

	- Call time out handling: **leave all settings to their default values**

8. Select **Save**. A Saved message will appear across the top of the page once the changes have been saved. This message will eventually disappear, and **Call Queue 1** will appear in the list of Call queues.

9. Leave all tabs open in your browser and proceed to the next task. 


### Task 6 - Create a Calling Policy 

In Microsoft Teams, calling policies control which calling and call forwarding features are available to users. Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on. A default global policy is created automatically, but admins can also create and assign custom calling policies. 

As part of her Microsoft Teams pilot project, Holly Dickson has been tasked with creating a custom calling policy for Adatum. Instead of customizing the default global policy, she will follow best practice guidelines and create her own customized policy that will be used as Adatum’s default policy.

1. On **LON-DC1** you should still have the **Microsoft Teams admin center** open from the prior task. In the left-hand navigation pane, under the **Voice** group, select **Calling policies.**

2. In the **Calling policies** window, scroll down through the list to see the predefined calling policies and then select **+Add** in the menu bar that appears above the list of calling policies.

3. In the **Calling policies\Add** window, enter **Default Adatum Calling Policy** in the **Add new calling policy** field at the top of the form.

4. Scroll down the page and select the following values for each setting:

	- Make private calls: **On**

	- Call forwarding and simultaneous ringing to people in your organization: **Off**

	- Call forwarding and simultaneous ringing to external phone numbers: **On**

	- Voicemail is available for routing inbound calls: **Enabled**

	- Inbound calls can be routed to a call group: **On**

	- Allow delegation for inbound and outbound calls: **Off**

	- Prevent toll bypass and send calls through the PSTN: **On**

	- Busy on busy is available when in a call: **On**

	- Allow web PSTN calling: **On**

5. Select **Save**. A Saved message will appear across the top of the page once the changes have been saved. This message will eventually disappear, and **Default Adatum Calling Policy** will appear in the list of Calling policies. Note how it is flagged as a Custom policy.

6. Leave all tabs open in your browser and proceed to the next task. 
 

### Task 7 – Manage External Access

With Microsoft Teams’ external access feature, Teams users from other domains can participate in your chats and calls. You can also block the users in specific domains from joining chats and calls. 

As part of her Microsoft Teams pilot project, Holly Dickson wants to block communication with users from a specific domain (spam.com) that has been the source of multiple spam attacks within Adatum over the past year. At the same time, Holly wants to allow communication with the users from another domain (microsoft.com) that is one of Adatum's key business partners.

1. On **LON-DC1** you should still have the **Microsoft Teams admin center** open from the prior task. In the left-hand navigation pane, under the **Org-wide settings** group, select **External access.**

2. In the **External access** window, leave the first two settings involving Skype for Business/Teams and Skype users set to **On**. 

3. To add the domain in which you want to allow communication, select **+Add a domain** in the menu bar that appears above the list of domains.  

4. In the **Add a domain** window, enter the following information:

	- Domain: **microsoft.com**

	- Action to take on this domain: **Allowed**

5. Select **Done.** 

6. To add the blocked domain, in the **External access** window, select **Add a domain.**

7. In the **Add a domain** pane that appears on the right, enter the following information:

	- Domain: **spam.com**

	- Action to take on this domain: **Blocked**

8. Select **Done.**

9. In the **External access** window, validate that **microsoft.com** and **spam.com** are represented in the list of domains and that each has the appropriate Status.

10. Select **Save.**

11. Leave all tabs open in your browser and proceed to the next task. 


### Task 8 – Manage Guest Access

Microsoft Teams’ guest access feature is a tenant-level setting that is turned Off by default. Once this setting is turned On, you can configure settings for guests. IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and generate reports on guest user activity. 

As part of your Microsoft Teams pilot project for Adatum, you will turn on guest access and then customize a variety of the guest settings as defined by Adatum’s project team.

1. On **LON-DC1** you should still have the **Microsoft Teams admin center** open from the prior task. In the left-hand navigation pane, under the **Org-wide settings** group, select **Guest access.**

2. In the **Guest access** window, set the **Allow guest access in Teams** setting to **On**. 

3. Once you set this switch to **On**, a variety of additional settings are displayed. Scroll down the page and select the following values for each setting:

	- Calling

		- Make private calls: **Off**

	- Meeting

		- Allow IP video: **On**

		- Screen sharing mode: **Entire screen**

		- Allow Meet Now: **On**

	- Messaging

		- Edit sent messages: **Off**

		- Delete sent Messages: **Off**

		- Chat: **On**

		- Use Giphy in conversations: **Off**

		- Giphy content rating: **Strict**

		- Use Memes in conversations: **Off**

		- User Stickers in conversations: **Off**

		- Allow immersive reader for viewing messages: **On**

4. Select **Save.** Note the message that displays indicating it can take a couple of hours for the changes to take effect. This message does not automatically disappear, so close this message by selecting the **X** that appears at the right-side of the message; otherwise, the message will remain at the top of your screen even as you navigate to other pages.

5. Leave all tabs open in your browser and proceed to the next task. 


### Task 9 – Manage Teams Settings

Microsoft Teams includes a variety of global settings that control performance within Teams. As part of her Microsoft Teams pilot project, Holly Dickson will configure a number of these settings as determined by Adatum’s project team.

1. On **LON-DC1** you should still have the **Microsoft Teams admin center** open from the prior task. In the left-hand navigation pane, under the **Org-wide settings** group, select **Teams settings.**

2. In the **Teams settings** window, select the following values for each setting:

	- Notifications and feeds
	
		- Suggested feeds can appear in a user's activity feed: **On**
		
	- Tagging
		
		- Tags are managed by: **Team owners and members**

		- Let team owners override who can manage tags: **On**

		- Suggested tags: **Sales** (press the space bar after entering this value); **Manufacturing** (press the space bar after entering this value); **Accounting** (press the space bar after entering this value)

		- Let custom tags be created: **On**

	- Email integration

		- Allow users to send emails to a channel email address: **On**

		- Accept channel email from these SMTP Domains: **microsoft.com** (press the space bar after entering this value)

	- Files

		- Citrix files: **On**

		- DropBox: **Off**

		- Box: **Off**

		- Google Drive: **On**

		- Egnyte: **Off**

	- Organization

		- Show Organization tab in chats: **On**

	- Devices

		- Require a secondary form of authentication to access meeting content: **No access**

		- Set content PIN: **Required for outside scheduled meeting**

		- Resource accounts can send messages: **On**

	- Search by name

		- Scope directory search using an Exchange address book policy: **On**

3. Select **Save.** Note the message that appears at the top of the form that it may take a few hours to see these changes applied.

4. Leave all tabs open in your browser and proceed to the next task. 

# End of Lab 8