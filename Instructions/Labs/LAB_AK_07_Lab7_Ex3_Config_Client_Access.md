# Module 7 - Lab 7 - Exercise 3 - Configuring client access policies

Outlook on the web enables Adatum's users to access their mailboxes through a web browser. After Adatum created its Microsoft 365 tenant with Exchange Online, the tenant included a single Outlook Web App policy titled OWAMailboxPolicy-Default. This policy defines Outlook on the web settings for all users. However, Holly Dickson, Adatum's Enterprise Admin, wants to create an additional Outlook on the web policy that applies to a specific user (in this case, Patti Fernandez). By verifying whether a user-specific policy such as this works, Holly will be able to vary the Outlook on the web settings for users with different needs.

Holly will then configure a mailbox policy for mobile devices that requires a password and sets the parameter for password length. Holly will then create a mobile device access policy that places any new devices into quarantine, at which point the device must be approved to be removed from quarantine so that it can send and receive messages. 

## Task 1: Configure an Outlook Web App policy

1. You should still be logged into LON-CL1 as the **Administrator** with a password of **Pa55w.rd**. 

2. Your Edge browser should be open from the prior exercise, with tabs open for the **Microsoft Office Home** page, the **Microsoft 365 admin center**, and the **Exchange admin center**. You should still be signed into Microsoft 365 as Holly Dickson. <br/>

	If you closed the Exchange admin center tab after the prior lab exercise, then in the **Microsoft 365 Admin center**, under **Admin Centers** in the left-hand navigation pane, select **Exchange**.

3. In the **Exchange admin center**, in the left-hand navigation pane, select **permissions**.

4. On the **permissions** page, the **admin roles** tab at the top of the page is displayed by default. Select the **Outlook Web App policies** tab.

5. On the the **Outlook Web App policies** tab, note the existing Outlook Web App policy titled **OWAMailboxPolicy-Default**. This policy defines Outlook on the web settings for all users. <br/>

	Since Holly wants to add a new policy, select the **plus (+) sign** icon on the menu bar. 

6. In the **new Outlook Web App mailbox policy** window, enter **Limited features** in the **Policy name** field. Note - This policy is titled **Limited features** since it reduces the number of features that will be enabled for the policy.

7. The window displays a list of features that will be enabled for this Outlook Web App mailbox policy. The majority of these features are selected by default. Clear the check boxes for the following features that Holly does not want included in this custom policy:

	- **Instant messaging**

	- **Text messaging**

	- **Unified messaging**

	- **LinkedIn contact sync**

	- **Journaling**

8. At the bottom of the window, under **Private computer or OWA for devices**, clear the **Direct file access** check box, select **Save**, and then select **OK** once the information has been successfully saved.

9. In the **Exchange admin center**, in the left-hand navigation pane, select **recipients**.

10. On the **recipients** page, the **mailboxes** tab at the top of the page is displayed by default. In the list of user mailboxes, select **Patti Fernandez** and then select the **pencil (Edit)** icon on the menu bar.

11. In the **Patti Fernandez** window, in the left-hand navigation pane, select **mailbox features**. <br/>

	If you receive a **Warning** dialog box indicating the user hasn't logged on to the mailbox, so there is no data to return, select **OK**.

12. Scroll down to the **Email Connectivity** section and select **View details**.

13. In the **Outlook Web App mailbox policy** window, select **Browse**. This displays the list of existing Outlook Web App policies. Select **Limited features**, select **OK**, and then select **Save**.

14. In the **Patti Fernandez** window, select **Save** and then select **OK** once the information is successfully saved.

15. You will now open **Outlook 2016**. Select the Windows icon in the bottom left-hand corner of the taskbar. In the program menu that appears, scroll down and select **Outlook 2016**. <br/>

	If a **Microsoft Office Activation Wizard** appears that indicates this copy of Microsoft Office is not activated, select **Close**.

16. By default Outlook should open for the tenant admin account (the MOD Administrator, whose email address is admin@M365xZZZZZZ.onmicrosoft.com). However, if you are instead prompted for user credentials in a **Windows Security** dialog box, enter **admin@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is the tenant ID provided by your lab hosting provider), and enter the tenant admin password provided by your lab hosting provider. 

17. In **Outlook 2016**, select **New Email**.

18. In the **new email** window, select the **To** button, and in the list of users that appears, select **Patti Fernandez**, select **To**, and then select **OK**.

19. In the **Subject** box, enter **Attachment Test**.

20. In the ribbon, select **Attach File**, and then Select **Browse This PC**.

21. In the **Insert File** window, browse to **C:\Windows\Logs\DISM**, select **dism.log**, and then select **Insert**.

22. Select **Send**.

23. After sending the email, close Outlook 2016.

24. Switch to **LON-CL2**.

25. **Outlook on the web** should still be open from a previous lab; however, you should be logged in as the MOD Administrator from the first exercise in this lab. Therefore, you must log out from Outlook as the MOD Administrator and log back in as Patti. <br/>

	To do so, select the MOD Administrator's user icon (the circle with the **MA** initials) in the upper right corner of the screen, then select **Sign out** in the **My account** window, enter **https://outlook.office365.com** in the address bar, sign in as Patti Fernandez (**PattiF@M365xZZZZZZ.onmicrosoft.com**, where ZZZZZZ is the tenant ID provided by your lab hosting provider), and enter the password assigned to the tenant admin account by your lab hosting provider.

26. In Patti's **Inbox**, select the email that you just sent from the **MOD Administrator** that contains the **Attachment Test** subject.

27. Select the **dism.log** message attachment.

28. A message should appear indicating that you do not have permission to download files. <br/>

	**Note:** In some cases, it may take a few minutes for the new Outlook Web App mailbox policy to take effect, so you may not see this message at this time.

29. Close the message attachment window.

30. Leave Outlook on the web open for Patti Fernandez.

31. Leave the Edge browser open and and all its tabs.


## Task 2: Configure mobile-device access

In this task, you will create a mobile device access policy that places any new devices into quarantine, at which point the device must be approved to be removed from quarantine so that it can send and receive messages. 

1. Switch to **LON-CL1**, where you should still be logged in as the **Administrator** with a password of **Pa55w.rd**. 

2. Your Edge browser should be open from the prior exercise, with tabs open for the **Microsoft Office Home** page, the **Microsoft 365 admin center**, and the **Exchange admin center**. You should still be signed into Microsoft 365 as Holly Dickson. <br/>

	If you closed the Exchange admin center tab after the prior lab exercise, then in the **Microsoft 365 Admin center**, under **Admin Centers** in the left-hand navigation pane, select **Exchange**.

3. In the **Exchange admin center**, in the left-hand navigation pane, select **mobile**.

4. On the **mobile** page, the **mobile device access** tab at the top of the page is displayed by default.

5. On the **mobile device access** tab, under the **Exchange ActiveSync Access Settings** section, select the **edit** button that appears at the far right of the screen.

6. In the **Exchange ActiveSync access settings** window, under the **Connect Settings** section, select the **Quarantine – Let me decide to block or allow later** option.

7. Under the **Quarantine Notification Email Messages** section, select the **plus (+) sign (Add) ** icon to add an administrator to receive email messages when a mobile device is quarantined. 

8. In teh **Select Administrators** window, in the list of users, select **MOD Administrator**, select **add**, and then Select **OK**.

9. In the **Exchange ActiveSync access settings** window, select **Save**.

10. Leave the Edge browser open and and all its tabs.

## Task 3: Configure a mailbox policy for mobile devices

In this task, you will configure a mailbox policy for mobile devices that requires a password and sets the parameter for password length.

1. You should still be logged into **LON-CL1** as the **Administrator** with a password of **Pa55w.rd**. 

2. Your Edge browser should be open from the prior exercise, with tabs open for the **Microsoft Office Home** page, the **Microsoft 365 admin center**, and the **Exchange admin center**. You should still be signed into Microsoft 365 as Holly Dickson. <br/>

	If you closed the Exchange admin center tab after the prior lab exercise, then in the **Microsoft 365 Admin center**, under **Admin Centers** in the left-hand navigation pane, select **Exchange**.

3. In the **Exchange admin center**, you should still be displaying the **mobile** tab in the left-hand navigation pane..

4. On the **mobile** page, the **mobile device access** tab at the top of the page should still be displayed from the prior task. Select the **mobile device mailbox policies** tab.

5. On the **mobile device mailbox policies** tab, select the **Default (default)** policy and then select the **pencil (Edit)** icon on the menu bar.

6. In the **Default** window, select the **security** tab in the left-hand navigation pane.

7. In the **security** tab, select the **Require a password** check box that appears at the top of the window.

8. Select the **Allow simple passwords** check box (if it's not already selected).

9. Select the **Minimum password length** check box, enter a value of **6**.

10. In the **Password recycle count** check box, enter a value of **5**, select **Save**, and then select **OK** once the information is successfully saved.

11. Leave the Edge browser and all its tabs open.

# End of Lab 7

 
