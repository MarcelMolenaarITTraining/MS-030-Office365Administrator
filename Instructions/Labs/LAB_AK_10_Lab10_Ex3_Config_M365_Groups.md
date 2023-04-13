# Module 10 - Lab 10 - Exercise 3 - Configuring Microsoft 365 groups

Holly Dickson is ready to finalize user collaboration in Microsoft 365 by implementing Microsoft 365 groups, which help in collaboration and teamwork, are available across all Microsoft 365 services, and are highly integrated with all Microsoft 365 services. Microsoft 365 groups, which are part of Azure Active Directory, are only available in Microsoft 365. Each Microsoft 365 group has a mailbox, a calendar, a Microsoft OneNote notebook, and a OneDrive for Business site collection.

In this exercise, Holly will configure a private Microsoft 365 group through the Microsoft 365 admin center. For comparison purposes, she will then create a public group through Windows PowerShell. She will complete this process by exploring the Microsoft 365 group components. 



### Task 1 - Configure a private Microsoft 365  group

1. Switch to **LON-CL1**, where you should still be logged in as the **Administrator** with a password of **Pa55w.rd**.

2. In the previous lab exercise involving Microsoft Yammer, you logged into Microsoft 365 as Holly Dickson. In your Edge browser, you should still have a tab open for the **Microsoft Office Home** page. In the the **Microsoft Office Home** page, select **Admin** to open the **Microsoft 365 admin center**.

3. In the **Microsoft 365 admin center**, select **Groups** in the left navigation pane and then select **Active groups**.

4. In the **Active Groups** window, select **Add a group** on the menu bar at the top of the page.

5. In the **Choose a group type** pane that appears, the **Microsoft 365** group type is selected by default. Accept this value by selecting **Next**.

6. In the **Set up the basics** window, enter **Finance** in the **Name** field and **Collaboration group for the Finance team** in the **Description field** and then select **Next** (Note - if you leave the **Description** field blank, you must still select it to enable the **Next** button).

7. In the **Assign owners** window, enter **MOD** in the **Owners** field, which will display the list of active users whose first name starts with MOD. Select **MOD Administrator** and then select **Next**.

8. In the **Edit settings** window, enter **Finance** in the **Group email address** field. <br/>

	**Note:** To the right of the **Group email address** field is the domain field. It’s already prefilled with the **M365xZZZZZZ.onmicrosoft.com** domain, which is set as Adatum's Default domain. This is different from adding users in that no other domains appear; therefore, you must leave this value as is.   <br/>

	After configuring this field, the Finance group email address should appear as: **Finance@M365xZZZZZZ.onmicrosoft.com** <br>

	After configuring the email address, under the **Privacy** section, select **Private**, and leave the check box selected to **Create a team for this group**. Select **Next**.

9. On the **Review and finish adding group** window, review the information and if anything needs to be changed, select the appropriate **Edit** option; otherwise, select the **Create group** button at the bottom of the page.

10. On the **New group created** window, note the message that appears at the top of the page that indicates it may take up to 5 minutes before the group appears in the list of active groups. Select **Close**

11. On the **Active groups** window, select **Refresh** on the menu bar to refresh the list of active groups. You may have to wait a few minutes and refresh again. Once the **Finance** group appears in the list, select the group.

12. In the **Finance** pane that appears, the **General** tab is displayed by default. Select the **Members** tab. 

13. In the **Members** tab, under the **Members** group, select **View all and manage members**.

14. In the **Finance** group window, select **+Add members**. This displays the list of current users.

15. In the list of users, select **Joni Sherman** and then select **Save**. 

16. Select **Close**. This displays the list of users for this group. Select **Close** again. 

17. On the **Finance** window, select the **X** in the upper right-hand corner to close the window.

18. Leaver your Edge browser and all its tabs open and proceed to the next task.

### Task 2 - Configure a public Microsoft 365  group with Windows PowerShell

1. On **LON-CL1**, you should still be logged in as the **Administrator** with a password of **Pa55w.rd**.

2. Back in Lab 2, you installed the **Windows Azure Active Directory Module for Windows PowerShell**. If you still have Windows PowerShell open, then select it now on the taskbar; otherwise, open an elevated instance of **Windows PowerShell** (i.e. Run as administrator).

3. In **Windows PowerShell**, at the command prompt type the following command and then press Enter to store your administrative credentials as a macro ($cred):

		$cred = Get-Credential

4. In the **Windows PowerShell credential request** window, sign in as **admin@M365xZZZZZZ.onmicrosoft.com** (replace ZZZZZZ with the tenant ID provided by your lab hosting provider) and then enter (or copy and paste in) the tenant admin password provided by your lab hosting provider.

5. At the command prompt type the following command and then press Enter to create a session with Microsoft Exchange Online:

		$session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection

6. At the command prompt type the following command and then press Enter to  import the session into the PowerShell console (Ignore the warning message that is generated):

		Import-PSSession $Session –AllowClobber

7. At the command prompt type the following command and then press Enter to   create a new public Microsoft 365 group called Planning (replace ZZZZZZ with the tenant ID provided by your lab hosting provider):

		New-UnifiedGroup –DisplayName "Planning" -Alias "Planning" –EmailAddresses Planning@M365xZZZZZZ.onmicrosoft.com

8. At the command prompt type the following command and then press Enter to add the MOD Administrator as the owner for the group (replace ZZZZZZ with the tenant ID provided by your lab hosting provider):

		Add-UnifiedGroupLinks "Planning" –Links Admin@C –LinkType Owner


9. At the command prompt type the following command and then press Enter to add Ada Russell as a member of the group (replace ZZZZZZ with the tenant ID provided by your lab hosting provider):

		Add-UnifiedGroupLinks "Planning" –Links Ada@M365xZZZZZZ.onmicrosoft.com –LinkType Member

10. Minimize the Windows PowerShell window and proceed to the next task.



### Task 3 - Explore the Microsoft 365  group components

In this task, you will log into Microsoft 365 as the MOD Administrator, who is the owner of the Planning group. You will then see how the Planning group is accessible to the MOD Administrator in Outlook, since the MOD Administrator is an owner of this group. You will send an email from the MOD Administrator to the Planning group. You will also send a meeting request from the Planning group to Joni Sherman. You will then create a document for the Planning group. Finally, Joni Sherman will join the Planning group and verify that received the email from the MOD Admin to the Planning group, and that she can access the document created for the group.

1. On **LON-CL1**, you should still be logged in as the **Administrator** with a password of **Pa55w.rd**.

2. In your Edge browser, you should still be logged into Microsoft 365 as Holly Dickson. Sign out of Microsoft 365 as Holly, close all your browser tabs except for your sign out tab, and then navigate to **https://portal.office.com**. Log in as the **MOD Administrator (admin@M365xZZZZZZ.onmicrosoft.com)** with the tenant admin password. 
 
3. On the **Microsoft Office Home** tab, select **Outlook**.

4. In **Outlook**, scroll to the bottom of the folder list in the left-hand pane. Under the **Groups** section, select **Planning**.

5. In the **Planning** pane that appears, select **Send email**.  

6. In the message window, the Planning group is prefilled in the **To** field. Enter a subject and some text in the message and then select **Send**.

7. In the **Planning** pane, select the **calendar (Go to the group calendar)** icon that appears to the right of **Send email** the you previously selected. This will open a new tab in your browser and take you to the Planning group's calendar. 

8. In the **Planning group's calendar**, select **New event**. In the **Details** pane for this event, type **Planning group meeting** for the title, schedule it for tomorrow, and then select **Save**.

9. Close the tab for the Planning group's calendar.

10. In your Edge browser, in the **Mail - MOD Administrator** tab, select the calendar icon.  Ensure the Planning group's calendar synchronizes with the Admin’s personal calendar. 

11. In **Outlook**, scroll to the bottom of the folder list in the left-hand pane. Under the **Groups** section in the left-hand pane, select **Planning** once again.

12. In the **Planning** pane, select the **file (Go to the group files)** icon that appears to the right of **Send email** the you previously selected. 

13. In the **Documents** window for the Planning group, select **+New** in the menu bar at the top of the form. In the drop-down menu that appears, select **Word document**. 

14. In Word Online, type some text into the blank document. When you see **Saved** in the title bar, select **File** in the menu bar, select **Save as**, and then select **Rename**. In the **File name** window, enter **Planning Review** as the name of the document. Select the document and note the change to the file name at the top of the form. 

15. Close the Word Online tab in your Edge browser.

16. In the **Planning** group pane, if the original document name (**Document.docx**) appears in the list of files rather than the new name you assigned, select the **Refresh** icon to the left of the address bar. Once the Planning group's Files page refreshes, you should see the renamed document.

17. On LON-CL1, open a **New InPrivate Browsing** window in Microsoft Edge. You will log into Microsoft 365 as Joni Sherman. Because the **Planning** group is a Public group, Joni can add herself to the group. 

18. In the new **InPrivate** browsing window, enter **https://portal.office.com** in the address bar and then sign in as **JoniS@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is the tenant ID provided by your lab hosting provider) and the enter (or copy and paste in) the tenant admin's password provided by the lab hosting provider.

19. In the **Microsoft Office Home** page, select **Outlook**. 

20. In **Outlook**, scroll to the bottom of the folder list in the left-hand pane. Locate the **Groups** section, then right-click on **Groups** and in the menu that appears select **Discover groups**.

21. In the **Discover groups** window, enter **Planning** in the **Search for groups** field and then press Enter to search for the group.

22. The search should return the **Planning** group. Select the **Join** button. Once the **Join** button changes to **Joined group**, close the **Discover groups** window. 

23. In **Outlook**, in the folder pane on the left, the **Planning** group should now appear under the **Groups** section. Select the **Planning** group.

24. Verify that the email from the MOD Administrator to the Planning group appears. 

25. Select the **Go to group files** icon.

26. On the **Files** page, verify the **Planning Review.docx** file appears. This is the document the MOD Administrator created for the Planning group.

27. Close the InPrivate browsing session for Joni Sherman.

28. On the **Microsoft Office Home** page, select the user icon (the circle with MOD Administrator's **MA** initials in it) in the upper right-hand corner, and in the **My account** window that appears, select **Sign out**. Once you are signed out, close all other tabs, and then close Microsoft Edge.  


**Results**: After completing this exercise, you should have configured Microsoft Microsoft 365  groups at Adatum.

# End of Lab 10