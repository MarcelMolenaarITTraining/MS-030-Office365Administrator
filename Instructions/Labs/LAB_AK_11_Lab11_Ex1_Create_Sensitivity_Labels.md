# Module 11 - Lab 11 - Exercise 1 - Creating Sensitivity Labels

Adatum has transitioned to Microsoft 365 as its enterprise cloud solution. The company has been awarded several government contracts which work heavily with sensitive and classified products.

In your role as Holly Dickson, Adatum’s Enterprise Administrator, the company CTO has requested that you devise a solution for encrypting and securing messages when working in these related contracts. He has also requested that any references to “Project New Day” be automatically encrypted. This is a top-secret project, and it is imperative that no mention of this project be leaked outside the company.

In this lab, you will address your CTO's request by creating sensitivity labels that will be used for creating label policies. You will create sensitivity labels using the Microsoft 365 Security center as well as Windows PowerShell. While still satisfying your CTO's request, this plan will provide you with experience using each method as part of your pilot project. This way, you can later decide which approach you prefer when you transition from your pilot phase to the production phase. With your labels in place, you will then create a label policy - again, using both the Security center and PowerShell. 

**Important:** Sensitivity labels and policies can take up to 24 hours to propagate through the system and update the back-end servers. Unfortunately, with this training course nearing its end, you will not have time to verify your work by testing the labels and policies you created. However, it is hoped that this lab exercise will still provide you with experience and insight into the mechanics of creating sensitivity labels and policies, even though you cannot test them.


### Task 1 - Creating a test team

In your role as Holly Dickson, you will create a new Microsoft 365 group titled PND Group (for Project New Day, the name of which you want to avoid circulating through the company) that will be used as part of your sensitivity label testing in the upcoming tasks. 

1. In **LON-CL1**, you should still be logged in as the **Administrator** with a password of **Pa55w.rd**.

2. At the end of the prior lab, you logged out of Microsoft 365 as the MOD Administrator and closed Edge. Select the **Edge** icon on the taskbar and then enter the following URL in the address bar: **https://portal.office.com**.

3. In the **Pick an account** window, select **Holly Dickson** at **holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is the tenant ID provided by your lab hosting provider) and enter **Pa55w.rd** as her password.
 
4. On the **Microsoft Office Home** page select **Admin**.

5. On the **Microsoft 365 admin center**, in the left-hand navigation pane select **Groups**, and then select **Active groups**.

6. In the **Active Groups** window, select **Add a group** on the menu bar at the top of the page.

7. In the **Choose a group type** pane that appears, the **Microsoft 365** group type is selected by default. Accept this value by selecting **Next**.

8. In the **Set up the basics** window, enter **PND Group** in the **Name** field and **Group used for sensitivity label testing** in the **Description field** and then select **Next** (Note - if you leave the **Description** field blank, you must still select it to enable the **Next** button).

9. In the **Assign owners** window, enter **MOD** in the **Owners** field, which will display the list of active users whose first name starts with MOD. Select **MOD Administrator** and then select **Next**.

10. In the **Edit settings** window, enter **PNDgroup** in the **Group email address** field. <br/>

	**Note:** To the right of the **Group email address** field is the domain field. It’s already prefilled with the **M365xZZZZZZ.onmicrosoft.com** domain, which is set as Adatum's Default domain. This is different from adding users in that no other domains appear; therefore, you must leave this value as is.   <br/>

	After configuring this field, the PND Group email address should appear as: **PNDgroup@M365xZZZZZZ.onmicrosoft.com** <br>

	After configuring the email address, under the **Privacy** section, select **Private**, and leave the check box selected to **Create a team for this group**. Select **Next**.

11. On the **Review and finish adding group** window, review the information and if anything needs to be changed, select the appropriate **Edit** option; otherwise, select the **Create group** button at the bottom of the page.

12. On the **New group created** window, note the message that appears at the top of the page that indicates it may take up to 5 minutes before the group appears in the list of active groups. Select **Close**

13. On the **Active groups** window, select **Refresh** on the menu bar to refresh the list of active groups. You may have to wait a few minutes and refresh again. Once the **Finance** group appears in the list, select the group.

14. For security purposes, you have decided to add Diego Siciliani as an additional owner of this group. In the **PND Group** pane that appears, the **General** tab is displayed by default. Select the **Members** tab. 

15. In the **Members** tab, under the **Owners** group, select **View all and manage owners**.

16. In the **PND Group** group window, select **+Add owners**. This displays the list of current users, as well as the existing owner (the MOD Administrator).

17. In the Search field, enter **Diego**, select **Diego Siciliani**, and then select **Save**. 

18. Select **Close**. This displays the list of owners for this group. Select **Close** again. 

19. In the **Members** tab, under the **Members** group, select **View all and manage members**.

20. In the **PND Group** group window, select **+Add members**. This displays the list of current users.

21. In the list of users, it may be easier to enter the first few characters of each user's first name in the Search field rather than scrolling through the list of all on-premises users that were synchronized to Microsoft 365 in the earlier directory synchronization lab. <br/>

	Select **Isaiah Langer**, **Nestor Wilke**, and **Patti Fernandez** and then select **Save**. 

22. Select **Close**. This displays the list of users for this group. Select **Close** again. 

23. On the **PND Group** window, select the **X** in the upper right-hand corner to close the window.

24. Leave your Edge browser and all its tabs open and proceed to the next task.


### Task 2 - Creating Sensitivity Labels using the Security and Compliance Center

Holly has decided to test creating sensitivity labels using both the Microsoft 365 Security and Compliance Center and Windows PowerShell. In this task you will use the Security and Compliance Center for this portion of your test.

 
1. On **LON-CL1**, you should still be logged in as the **Administrator** with a password of **Pa55w.rd**.

2. In your Edge browser, you should still have a tab open for the **Microsoft Office Home** page and the **Microsoft 365 admin center** and you should still be logged in as Holly Dickson.<br/>

	Select the **Microsoft 365 admin center** tab.

3.	In the **Microsoft 365 admin center**, select **Show all** in the left navigation pane and then under **Admin centers**, select **Security**.

4.	In the **Office 365 Security and Compliance** center, in the left-hand navigation pane, select **Classification**, and then select **Sensitivity labels**.

5.	On the **Sensitivity** page, the **Labels** tab is displayed by default. On the menu bar above the list of labels, select **Create a label**. This initiates a wizard to create a new sensitivity label.

6.	In the **New sensitivity label** wizard, on the **Name and create a tooltip for your label** page, enter **Classified** in the **Name** field, and enter **For Official Use Only** in the **Description for Users** field. Select **Next**.

7. On the **Encryption** page, select the drop-down arrow in the **Encryption** field and then select **Apply**. This displays a number of encryption options.
 
8. In the **Assign Permissions now or let users decide?** field, select **Let users assign permissions when they apply the label**.

9. Select the **In Outlook, enforce restrictions equivalent to the Do Not Forward Option** check box.

10.	Select **Next**.

11.	On the **Content marking** page, select the toggle switch to turn **ON** Content Marking. This displays several additional options, which should be update in the following steps.

12. Select the **Add a watermark** check box and then select **Customize text**.

13. In the **Customize watermark text** window, enter the following information and then select **Save**: <br/>

	- Watermark text: **CLASSIFIED**
	- Font size: **48**
	- Font color: **RED**
	- Text layout: **Diagonal**

14. Select the **Add a header** check box and then select **Customize text**.

15. In the **Customize header text** window, enter the following information and then select **Save**: <br/>

	- Header text: **FOR OFFICIAL USE ONLY**
	- Font size: **12**
	- Font color: **Blue**
	- Align text: **Left**

16. Select the **Add a footer** check box and then select **Customize text**.

17. In the **Customize footer text** window, enter the following information and then select **Save**: <br/>

	- Footer text: **CONFIDENTIAL**
	- Font size: **12**
	- Font color: **Green**
	- Align text: **Left**

18. On the **Content marking** page, select **Next**.

19.	On the **Auto-labeling for Office apps** page, verify the switch is turned **OFF** (it should be by default; if not, select **OFF**) and then select **Next**.

20.	On the **Review your settings** page, review the entries that you made. If any need to be corrected, select the corresponding **Edit** option and make the necessary changes. When all settings are correct, select **Create label**.

21.	On the **Your label was created** page, select **Done**.

22. Leave your Edge browser and all its tabs open and proceed to the next task.


### Task 3 - Creating Sensitivity Labels using Windows PowerShell

Holly has decided to test creating sensitivity labels using both the Security and Compliance Center and Windows PowerShell. In this task you will use Windows PowerShell for this portion of your test.

**Note:** What Holly will learn from this task is that due to a current limitation, only the basic parameters for a sensitivity label can be updated in PowerShell at this time. The remaining parameters will have to be entered using the Security and Compliance Center.

 
1. On **LON-CL1**, you should still be logged in as the **Administrator** with a password of **Pa55w.rd**.

2. Select the **magnifying glass (Search)** icon in the bottom left corner of your taskbar and then enter **powershell** in the Search field. 

3. In the list of search results, right-click on **Windows PowerShell**, and in the menu that appears select **Run as administrator**.

4. Maximize your PowerShell window. In **Windows PowerShell**, at the command prompt type the following command and then press Enter: <br/>

		Set-ExecutionPolicy -ExecutionPolicy RemoteSigned

	You will be prompted to confirm whether you want to change the execution policy. Enter **A** for **[A] Yes to all**. 

5.	At the command prompt enter the following command and then press Enter: <br/>

		Import-Module ExchangeOnlineManagement

6. 	At the command prompt enter the following command and then press Enter (remember to replace ZZZZZZ with the tenant ID provided by your lab hosting provider: <br/>

		Connect-IPPSSession -UserPrincipalName Admin@M365xZZZZZZ.onmicrosoft.com

	You will then be prompted to enter the Password for the MOD Administrator account. Enter the tenant admin password and then seelct **Sign in**.

7. At the command prompt enter the following command and then press Enter to validate that your are connected to the Microsoft 365 Compliance center: <br/>

		Get-DlpSensitiveInformationType -Identity "Credit Card Number"

8.	At the command prompt enter the following command and then press Enter to create a new sensitivity label named “Secret”, set its Tooltip to “Use it for Government Contracts ONLY" and changes the text color to Red: <br/>

		New-Label -DisplayName Secret -Tooltip "For use with Government contracts ONLY" -AdvancedSettings @{Color="RED"} -Confirm

	While the command updated the Display Name, you will be prompted to enter the label's Name. At the **Name** prompt, enter **Secret** and then press Enter. <br/>

	The policy will be displayed and it will be enabled (Disabled = False).

9. At the command prompt enter the following command and then press Enter to apply a Description to the Secret label (**Note:** At this time, this is the only label parameter you can set in PowerShell without extensive Scripts from JSON): <br/>

		Set-Label -Identity Secret -Comment "For use with Government contracts ONLY"

10.	On the taskbar, select the Edge browser icon, and then select the **Security and Compliance** tab. You should still be in the **sensitivity** page and it should be displaying the **Labels** tab for this page. 

11. In the list of labels, the **Classified** label that you created earlier should be displayed. Select **Refresh** on the menu bar above the list of labels.

12.	In the list of labels, you should now see the **Classified** label that you created using the Security and Compliance Center and the **Secret** label that you created using Windows PowerShell. <br/>

	Select the **Secret** label.

13.	In the **Secret** pane that appears, note that only the Name, Display Name, and Description were provided at the time the label was created in PowerShell. As mentioned earlier, this is due to a current limitation where these are the only parameters that can be entered for a sensitivity label in PowerShell at this time. <br/>

	To enter the remaining parameters for this Secret label, select **Edit label**.

14. On the **Name and create a tooltip for your label** page, select **Next**.

15. On the **Encryption** page, select the drop-down arrow in the **Encryption** field and then select **Apply**. This displays a number of encryption options.
 
16. In the **Assign Permissions now or let users decide?** field, select **Let users assign permissions when they apply the label**.

17. Select the **In Outlook, enforce restrictions equivalent to the Do Not Forward Option** check box.

18.	Select **Next**.

19.	On the **Content marking** page, select the toggle switch to turn **ON** Content Marking. This displays several additional options, which should be update in the following steps.

20. Select the **Add a watermark** check box and then select **Customize text**.

21. In the **Customize watermark text** window, enter the following information and then select **Save**: <br/>

	- Watermark text: **CLASSIFIED**
	- Font size: **48**
	- Font color: **RED**
	- Text layout: **Diagonal**

22. Select the **Add a header** check box and then select **Customize text**.

23. In the **Customize header text** window, enter the following information and then select **Save**: <br/>

	- Header text: **TOP SECRET**
	- Font size: **12**
	- Font color: **Blue**
	- Align text: **Left**

24. Select the **Add a footer** check box and then select **Customize text**.

25. In the **Customize footer text** window, enter the following information and then select **Save**: <br/>

	- Footer text: **CONFIDENTIAL**
	- Font size: **12**
	- Font color: **Green**
	- Align text: **Left**

26. On the **Content marking** page, select **Next**.

27.	On the **Auto-labeling for Office apps** page, verify the switch is turned **OFF** (it should be by default; if not, select **OFF**) and then select **Next**.

28.	On the **Review your settings** page, review the entries that you made. If any need to be corrected, select the corresponding **Edit** option and make the necessary changes. When all settings are correct, select **Save label**.

29.	On the **Label updated** page, select **Done**.

30. Leave your Edge browser and all its tabs open and proceed to the next task.

	
### Task 4 - Creating Sensitivity Label Policies using the Security and Compliance Center

Holly has decided to test creating sensitivity label policies using both the Microsoft 365 Security and Compliance Center and Windows PowerShell. In this task you will use the Security and Compliance Center for this portion of your test.

1.	On **LON-CL1** you should still be in the **Security and Compliance** tab, which should be displaying the **sensitivity** page. You are currently displaying the **Labels** tab for this page. <br/>

	In the list of tabs across the top of the page, select **Label policies**.

2.	On the **Label policies** page, on the menu bar above the list of policies, select **Publish labels**. This initiates a wizard to create a new sensitivity label policies.

3.	In the **Create policy** wizard, on the **Choose sensitivity labels to publish** page, select **Choose sensitivity labels to publish**. 

4. On the **Sensitivity labels to publish** pane that appears, select **Classified** and then select **Add** (Note - you will publish the Secret label in the next task using Windows PowerShell).

5.	On the **Choose sensitivity labels to publish** page, select **Next**.

6.	On the **Publish to users and groups** page, you will define the users and groups to which this published label will be made available. Note that the **Users and groups** is set by default to **All**, which will include all users and groups in the organization. Select **Next**.

7.	On the **Policy Settings** page, leave the current selection of **None** and select **Next**.

8. On the **Name your policy** page, enter **Classified Policy** in the **Name** field and enter **This policy is used for sensitive information in Government contracts only**. Select **Next**.

9.	On the **Review and finish** page, review the entries that you made. If any need to be corrected, select the corresponding **Edit** option and make the necessary changes. When all settings are correct, select **Submit**.

10.	On the **New policy created** page, select **Done**.

11. Leave your Edge browser and all its tabs open and proceed to the next task.


### Task 5 - Creating Sensitivity Label Policies using Windows PowerShell

Holly has decided to test creating sensitivity label policies using both the Security and Compliance Center and Windows PowerShell. In this task you will use Windows PowerShell for this portion of your test.

**Note:** What Holly will learn from this task is that due to a current limitation, only the basic parameters for a sensitivity label can be updated in PowerShell at this time. The remaining parameters will have to be entered using the Security and Compliance Center.

 
1. On **LON-CL1**, you should still be logged in as the **Administrator** with a password of **Pa55w.rd**.

2. Windows PowerShell should still be open from a prior task. If so, then skip to the next step. However, if you closed PowerShell, then open an elevated instance of it now (Run as administrator) and run the following commands to re-establish your session: <br/>

		Set-ExecutionPolicy -ExecutionPolicy RemoteSigned

	You will be prompted to confirm whether you want to change the execution policy. Enter **A** for **[A] Yes to all**. <br/>

		Import-Module ExchangeOnlineManagement

		Connect-IPPSSession -UserPrincipalName Admin@M365xZZZZZZ.onmicrosoft.com 
		
		(remember to replace ZZZZZZ with the tenant ID provided by your lab hosting provider)	

	You will then be prompted to enter the Password for the MOD Administrator account. Enter the tenant admin password and then seelct **Sign in**. <br/>

3. At the command prompt enter the following command and then press Enter to create a new Sensitivity label policy named “Secret” using the secret Label that you created in the earlier task. This label policy will be applied to the PND Group group and will use the highest-level label as the default for documents and will automatically apply the label to emails and documents sent from this group. Do not forge to replace ZZZZZZ with the tenant ID provided by the lab hosting provider. <br/>

		New-LabelPolicy -Name "Secret policy" -Labels "Secret" -Comment "This policy is for the Microsoft 365 pilot project team related to Project New Day." -ModernGroupLocation PNDgroup@M365xZZZZZZ.onmicrosoft.com   -AdvancedSettings @{AttachmentAction="Automatic"}

4. At the command prompt enter the following command and then press Enter: <br/>

		Set-LabelPolicy -Identity "Secret policy" -AdvancedSettings @{DisableMandatoryInOutlook="True"}

5. On the taskbar, select the Edge browser icon, and then select the **Security and Compliance** tab. You should still be in the **sensitivity** page and it should be displaying the **Label policies** tab for this page. <br/>

	In the list of label policies, the **Classified** label that you created earlier should be displayed. Select **Refresh** on the menu bar above the list of labels.

6. In the list of label policies, you should now see the **Classified policy** that you created using the Security and Compliance Center and the **Secret policy** that you created using Windows PowerShell. <br/>

7. Close Windows PowerShell.

8. Leave your Edge browser and all its tabs open and proceed to the next lab.



# End of Lab 11