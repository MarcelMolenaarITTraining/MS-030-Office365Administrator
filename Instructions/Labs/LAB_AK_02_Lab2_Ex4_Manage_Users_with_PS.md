# Module 2 - Lab 2 - Exercise 4 - Managing Microsoft 365 users and groups with Windows PowerShell

Windows Powershell can improve the way an administrator can automate and streamline complicated or simple tasks that can be time-consuming when performed in the Microsoft 365 user interface. By entering commands directly to the tenant, tasks that would take hours by hand can be reduced to minutes or even seconds with PowerShell.

In this exercise, you will continue in your role as Holly Dickson. Holly wants to perform some basic user maintenance using Windows PowerShell. This will enable her to compare her experience creating and maintaining users in the Microsoft 365 admin center to performing the same tasks using Windows PowerShell.

To implement PowerShell in a Microsoft 365 deployment, you must first install the Microsoft Online Services Sign-In Assistant, which provides end user sign-in capabilities to Microsoft Online Services, such as Microsoft 365. This assistant installs client components that allow common applications, such as Microsoft Outlook, to authenticate to Microsoft Online Services. The Microsoft Online Services Sign-In Assistant can also provide an improved sign-in experience, such that end users can access Microsoft Online Services without having to re-enter their credentials (such as a user name or password). 

Once the Microsoft Online Services Sign-In Assistant is installed, you will  use Windows PowerShell to create new user accounts and assign them licenses, modify existing user accounts, create Microsoft 365 groups using, and configure user passwords. 

### Task 1 - Installing Microsoft Azure Active Directory module for Windows PowerShell

In this task you are going to lay the foundation for editing and managing the Microsoft 365 tenant with the use of PowerShell. The next step is to install the Microsoft Online Services Sign-In Assistant, which provides end user sign-in capabilities to Microsoft Online Services, such as Microsoft 365. 

The Microsoft Online Services Sign-In Assistant installs client components that allow common applications, such as Microsoft Outlook, to authenticate to Microsoft Online Services. The Microsoft Online Services Sign-In Assistant can also provide an improved sign-in experience, such that end users can access Microsoft Online Services without having to re-enter their credentials (such as a user name or password). This download is intended for IT professionals for distribution to managed client systems as part of a Microsoft 365 client deployment through System Center Configuration Manager (SCCM) or similar software distribution systems.

1. You should still be logged into the **LON-CL1** VM as the **Administrator** account with a password of **Pa55w.rd**.

2. Your **Edge** browser should still be open from the prior lab exercise. You should be logged into Microsoft 365 as Holly Dickson, and the browser should have tabs open for the **Microsoft Office Home** page and the **Microsoft 365 admin center**. <br>

	Open a new tab in your browser and then enter the following URL in the address bar: **http://aka.ms/t01i1o**

3. This will take you to the **Microsoft Download Center** for the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Select the **Download** button.

4. On the **Choose the download you want** page, select the **msoidcli_64.msi** check box and then Select **Next**.

5. In the notification bar that appears at the bottom of the page, once the **msoidcli_64.msi** file is saved, select **Open file**. 

6. On the **Do you want to run this file?** dialog box, select **Run**.

7. In the **Microsoft Online Services Sign-in Assistant Setup** wizard, select **I accept the terms in the License Agreement and Privacy Statement**, and then Select **Install**.

8. If a **Do you want to allow this app to make changes to your device** dialog box appears, select **Yes**.

9. On the **Completed the Microsoft Online Services Sign-in Assistant Setup Wizard** page, select **Finish**.

10. Close the tab in your Edge browser for the **Download Center**.

11. In the Search box in the bottom left corner of your taskbar, enter **powershell**. 

12. In the list of search results, right-click on **Windows PowerShell**, and in the menu that appears select **Run as administrator**.

13. If a **Do you want to allow this app to make changes to your device** dialog box appears, select **Yes**.

14. Maximize your PowerShell window. In **Windows PowerShell**, at the command prompt type the following command and then press Enter:<br/>

		Install-Module MSOnline
	
15. If you are prompted to install the **NuGet provider**, enter **Y** to select **[Y] Yes**. 

16. If you are prompted to confirm whether you want to install the module from an untrusted repository (PSGallery), enter **A** to select **[A] Yes to All.** 

17. Once the installation is complete, the screen will return to the Windows PowerShell command prompt. At the command prompt type the following command to install the Azure AD PowerShell module that you just retrieved in the earlier step and then press Enter: <br>

		Install-Module AzureADPreview 
	
18. If you are prompted to confirm whether you want to install the module from an untrusted repository (PSGallery), enter **A** to select **[A] Yes to All.** 

19. Once the installation is complete, the screen will return to the Windows PowerShell command prompt. You have now installed the **Windows Azure Active Directory PowerShell Module**.

20. Leave the Windows PowerShell window open and proceed to the next task.

### Task 2 - Create new users and assign licenses by using Windows PowerShell

In a previous lab exercise, you created new user accounts using the **Microsoft 365 admin center**. In this task, you will create two new users using Windows PowerShell, and you will assign each an **Office 365 E5** license. You will then delete one of the users and then restore the deleted user's account back to the Active users list. 

1. You should still be logged into the **LON-CL1** VM as the **Administrator** account with a password of **Pa55w.rd**.

2. You should still have the **Windows PowerShell** window open from the prior task. At the command prompt type the following command that connects your PowerShell session to the Microsoft Online Service and then press Enter:<br/>

		Connect-MsolService
	
3. In the **Sign in** dialog box that appears, log in as **Holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) with a password of **Pa55w.rd**. 

4. PowerShell's execution policy settings dictate what PowerShell scripts can be run on a Windows system. Setting this policy to **Unrestricted** enables Holly to load all configuration files and run all scripts. At the command prompt, type the following command and then press Enter:   <br/>

		Set-ExecutionPolicy unrestricted

	‎If you are prompted to verify that you want to change the execution policy, enter **A** to select **[A] Yes to All.** 

5. At the command prompt, type the following command and then press Enter to create a new user named **Catherine Richard** with a password of **Pa55w.rd** and a location set to **CH**. In Catherine's username in the following command, don't forget to replace **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. Setting the -ForceChangePassword parameter to false means Catherine will not have to change her password when she signs in the first time. <br>

		New-MsolUser –UserPrincipalName Catherine@M365xZZZZZZ.onmicrosoft.com –DisplayName “Catherine Richard” –FirstName “Catherine” –LastName “Richard” –Password ‘Pa55w.rd’ –ForceChangePassword $false –UsageLocation “CH”

6. At the command prompt, type the following command and then press Enter to create a new user named **Tameka Reed** with a password of **Pa55w.rd** and a location set to **CH**. In Tameka's username in the following command, don't forget to replace **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. <br>

		New-MsolUser –UserPrincipalName tameka@M365xZZZZZZ.onmicrosoft.com –DisplayName “Tameka Reed” –FirstName “Tameka” –LastName “Reed” –Password ‘Pa55w.rd’ –ForceChangePassword $false –UsageLocation “CH”

7. At the command prompt, type the following command and then press Enter to display all the users who are unlicensed: <br>

		Get-MsolUser -UnlicensedUsersOnly

8. At the command prompt, type the following command and then press Enter to show all available licenses inside Adatum's Microsoft 365 deployment: <br>

		Get-MsolAccountSku

	The ENTERPRISEPREMIUM license is the Office 365 E5 license that was assigned to most of the user accounts. Note that 15 licenses were purchased with Adatum's subscription (Active Units) and 13 have been assigned (Consumed Units). That leaves two licenses available to be assigned. 

9. At the command prompt, type the following command and then press Enter to assign a license to **Catherine Richard**. In the command, don't forget to replace the two instances of **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. This command will assign an Enterprise E5 license to Catherine. <br>

		Set-MsolUserLicense -UserPrincipalName Catherine@M365xZZZZZZ.onmicrosoft.com –AddLicenses “M365xZZZZZZ:ENTERPRISEPREMIUM”

10. At the command prompt, type the following command and then press Enter to assign a license to **Tameka Reed**. In the command, don't forget to replace the two instances of **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. This command will assign an Enterprise E5 license to Tameka. <br>

		Set-MsolUserLicense -UserPrincipalName Tameka@M365xZZZZZZ.onmicrosoft.com –AddLicenses “M365xZZZZZZ:ENTERPRISEPREMIUM”

11. At the command prompt, type the following command and then press Enter to block Catherine from signing in. In the command, don't forget to replace the **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. <br>

		Set-MsolUser -UserPrincipalName Catherine@M365xZZZZZZ.onmicrosoft.com -BlockCredential $true

12. At the command prompt, type the following command and then press Enter to delete Catherine's user account. In the command, don't forget to replace the **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. Note - This command will delete Catherine's user account without requesting a confirmation. <br>

		Remove-MsolUser –UserPrincipalName Catherine@M365xZZZZZZ.onmicrosoft.com –Force

13. At the command prompt, type the following command and then press Enter to view the **Deleted Users** list: <br>

		Get-MsolUser –ReturnDeletedUsers

14. Verify that Catherine Richard is in the list of deleted users. Note that it specifies that she is still licensed.

15. At the command prompt, type the following command and then press Enter to restore Catherine's user account to an active user status. In the command, don't forget to replace the **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. <br>

		Restore-MsolUser –UserPrincipalName Catherine@M365xZZZZZZ.onmicrosoft.com

16. At the command prompt, type the following command and then press Enter to view the list of deleted users: <br>

		Get-MsolUser –ReturnDeletedUsers

17. Since Catherine should have been the only deleted user prior to being restored, there will be no users to display, so PowerShell should simply display the command prompt.

18. At the command prompt, type the following command and then press Enter to view the list of active users: <br>

		Get-MsolUser

19. Verify that Catherine Richard is in the active users list.

20. At the command prompt, type the following command and then press Enter to unblock Catherine from signing in to Microsoft 365. In the command, don't forget to replace the **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. <br>

		Set-MsolUser -UserPrincipalName Catherine@M365xZZZZZZ.onmicrosoft.com -BlockCredential $false

21. Leave the Windows PowerShell window open and proceed to the next task.


### Task 3 - Bulk Import users using Windows PowerShell

In this task, you will use Windows PowerShell to import a csv file of new user account records into Microsoft 365. The file path is **C:\labfiles\O365Users.csv**.

At first you will attempt to import the users and assign each an **Office 365 E5** license. Based on the outcome of that import, you will make an adjustment to the csv file and re-import the users without a license. 

1. You should still be logged into the **LON-CL1** VM as the **Administrator** account with a password of **Pa55w.rd**.

2. You should still have the **Windows PowerShell** window open from the prior task.

3. On the taskbar at the bottom of the screen, select the **File Explorer** icon.

4. In **File Explorer** navigate to **C:\labfiles**, right-click on the **O365users.csv** file, and in the menu that appears select **Open with** and then Select **Notepad**.

5. In **Notepad**, review the records for each user account. Note the domain portion of each username is **yourdomain.hostdomain.com**. You need to replace this with **M365xZZZZZZ.onmicrosoft.com** for each user (where you will enter the unique tenant ID provided by your lab hosting provider in place of ZZZZZZ). The easiest way to do this is by doing a Find and Replace. In the menu bar at the top of the **Notepad** window, select **Edit** and then select **Replace**.

6. In the **Replace** window, copy **yourdomain.hostdomain.com** from one of the records and paste it in the **Find what** field, enter **M365xZZZZZZ.onmicrosoft.com** in the **Replace with** field (replacing ZZZZZZ with your tenant ID), and then select **Replace All**. 

7. In **Notepad**, review the records for each user account. Note the license assigned to each user is **adatumyyxxxx:ENTERPRISEPACK**. You need to replace this with **M365xZZZZZZ:ENTERPRISEPREMIUM** for each user (where you will enter the unique tenant ID provided by your lab hosting provider in place of ZZZZZZ). The easiest way to do this is by doing a Find and Replace. The **Replace** window should still be open; if you closed it after the prior step, then open it again. 

8. In the **Replace** window, copy **adatumyyxxxx:ENTERPRISEPACK** from one of the records and paste it in the **Find what** field, enter **M365xZZZZZZ:ENTERPRISEPREMIUM** in the **Replace with** field (replacing ZZZZZZ with your tenant ID), and then select **Replace All**. 
 
9. Close the **Replace** window.

10.  Select the X in the upper right corner of the **Notepad** window to close it. In the **Notepad** dialog box that appears asking if you want to save the changes to the O365Users.csv file, select **Save**.

11. Close File Explorer.

12. In **Windows PowerShell**, copy the following command and paste it in at the command prompt and then press Enter to bulk import the users from the O365Users.csv file into Microsoft 365:

		Import-Csv -Path C:\labfiles\O365Users.csv | ForEach-Object { New-MsolUser -UserPrincipalName $_."UPN" -AlternateEmailAddresses $_."AltEmail" -FirstName $_."FirstName" -LastName $_."LastName" -DisplayName $_."DisplayName" -BlockCredential $False -ForceChangePassword $False -LicenseAssignment $_."LicenseAssignment" -Password $_."Password" -PasswordNeverExpires $True -Title $_."Title" -Department $_."Department" -Office $_."Office" -PhoneNumber $_."PhoneNumber" -MobilePhone $_."MobilePhone" -Fax $_."Fax" -StreetAddress $_."StreetAddress" -City $_."City" -State $_."State" -PostalCode $_."PostalCode" -Country $_."Country" -UsageLocation $_."UsageLocation" }

13. Notice what happens when you run this command. Each of users in the import file were rejected because Adatum had already consumed all of its Office 365 E5 licenses; therefore, there were no available licenses to assign to these users.<br>

	To work around this for the purposes of your VM lab environment, you will remove the license assignment field from the .csv file. This will add each user and not assign them a license. To do so, open **File Explorer** and then use **Notepad** to open the **O365Users.csv** file. 

14. In the **O365Users.csv** file, the first record is the header record. Delete the **LicenseAssignment** field and the comma that follows it.<br>

	Then in each user record, delete the **M365xZZZZZZ:ENTERPRISEPREMIUM** value and the comma that follows it.

15. In **Notepad**, select **File** in the menu bar at the top of the window, and then in the drop-down menu select **Save As**. In the File Explorer window that appears, it's currently pointing to the **C:\Labfiles** folder. In the **File name** field, **O365Users.csv** appears by default. Change the file name to **O365Users_No_Licenses.csv** and then select **Save**.

16. Close **Notepad**.

17. Re-run the Import-Csv command in step 12. However, before you run the command, you must update the command by removing the **-LicenseAssignment $_."LicenseAssignment"** parameter, and you must change the file name to **O365Users_No_Licenses.csv**.

18. Notice what happens when you run this command. Each of users in the import file is successfully added into Microsoft 365, and the **isLicensed** column displays **False** for each record. This indicates that each user was added with no license.

19. At the command prompt, type the following command and then press Enter to view the list of active users: <br>

		Get-MsolUser

20. Verify the new users from the .csv file are included in the active users list. 

21. Minimize the PowerShell window and switch back to your Edge browser. 

22. In the **Microsoft 365 admin center** navigate to the **Active users** list. Review the active users and verify the new users you just imported in PowerShell appear in the list, along with Catherine Richard and Tameka Reed, who you added individually using PowerShell. 

23. In the **Microsoft 365 admin center**, in the left-hand navigation pane, select **Show all** (if necessary) to display all the menu options. Under the **Admin centers** section, select **Exchange**.

24. In the **Exchange admin center**, in the left-hand navigation pane, select **recipients**. In the **recipients** window, the **mailboxes** tab is displayed by default. Review the mailboxes. Note that no Exchange mailbox was created for any of the unlicensed users.

25. Close the **mailboxes - Microsoft Exchange** tab in your browser, which takes you back to the **Microsoft 365 admin center** tab. 

26. Leave Windows PowerShell and your Edge browser open and proceed to the next task.



### Task 4 - Configure groups and group membership by using Windows PowerShell

In a previous lab exercise, you used the Microsoft 365 admin center to create several Microsoft 365 groups. In this task, you will use PowerShell to create a group and add two members to the group.

1. You should still be logged into the **LON-CL1** VM as the **Administrator** account with a password of **Pa55w.rd**.

2. Towards the end of the prior task, you minimized the **Windows PowerShell** window. Select the **PowerShell** icon on the taskbar to maximize the window. 

3. In **Windows PowerShell**, at the command prompt type the following command and press Enter to create a new Microsoft 365 group called **Marketing department users**: <br>

		New-MsolGroup –DisplayName “Marketing” –Description “Marketing department users”

4. At the command prompt, type the following command and then press Enter to configure a variable for the group. This command will create a macro cmdlet that will retrieve all objects that belong to Marketing. <br>

		$MktGrp = Get-MsolGroup | Where-Object {$_.DisplayName -eq "Marketing"}

5. At the command prompt, type the following command and then press Enter to configure a variable for the first user account. This command will create a macro cmdlet that retrieves all users that have a display name Catherine Richard.

		$Catherine = Get-MsolUser | Where-Object {$_.DisplayName -eq "Catherine Richard"}

6. At the command prompt, type the following command and then press Enter to configure a variable for the first user account. This command will create a macro cmdlet that retrieves all users that have a display name Tameka Reed.

		$Tameka = Get-MsolUser | Where-Object {$_.DisplayName -eq "Tameka Reed"}

7. At the command prompt, type the following command and then press Enter to add Catherine Richard to the newly created Marketing department users group:

		Add-MsolGroupMember -GroupObjectId $MktGrp.ObjectId -GroupMemberType "User" -GroupMemberObjectId $Catherine.ObjectId

8. At the command prompt, type the following command and then press Enter to add Tameka Reed to the newly created Marketing department users group:

		Add-MsolGroupMember -GroupObjectId $MktGrp.ObjectId -GroupMemberType "User" -GroupMemberObjectId $Tameka.ObjectId

9. At the command prompt, type the following command and then press Enter to retrieve all members associated with the new Marketing department users group:

		Get-MsolGroupMember -GroupObjectId $MktGrp.ObjectId

10. Verify that Catherine Richard and Tameka Reed appear in the list of group members for the Marketing department users group.

11. Leave Windows PowerShell open and proceed to the next task.




## Task 5: Configure user passwords by using Windows PowerShell

In a previous lab, you used the Microsoft 365 admin center to update Adatum's password policy by first changing the expiration period from 90 days to 14. With a notification period of 14 days, you verified that a user who signed into Microsoft 365 received a notification message indicating their password was due to expire in 13 days. You then reset the expiration days from 14 days back to 90. 
For this task, you will use PowerShell to set the expiration days from 90 to 60, and the notification period from 14 days to 10.

In a previous lab, you reset a user's password using the Microsoft 365 admin center. In this task, you will change a user's password using PowerShell. You will also use PowerShell to update every user account by turning off the **Password Never Expires** parameter for all users. This will ensure that all users will be subject to the new password policy in which their password will expire after 60 days.

1. You should still be logged into the **LON-CL1** VM as the **Administrator** account with a password of **Pa55w.rd**.

2. In **Windows PowerShell**, at the command prompt, type the following command and then press Enter to update the password policy for Adatum's **M365xZZZZZZ.onmicrosoft.com** domain. You will change the expiration period to **60 days** and the notification period to **10 days**. In the command, don't forget to replace the **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. <br>

		Set-MsolPasswordPolicy -DomainName “M365xZZZZZZ.onmicrosoft.com” –ValidityPeriod “90” -NotificationDays “10”

3. At the command prompt, type the following command and then press Enter to change Tameka Reed's password to **P@$$W0rd**. In the command, don't forget to replace the **ZZZZZZ** with the unique tenant ID provided by your lab hosting provider. <br>

		Set-MsolUserPassword –UserPrincipalName “Tameka@M365xZZZZZZ.onmicrosoft.com” –NewPassword ‘P@$$W0rd’

4. At the command prompt, type the following command and then press Enter to turn off **Password Never Expires** parameter for all users. This will ensure that all users will be subject to the new password policy in which their password will expire after 60 days.

		Get-MsolUser | Set-MsolUser –PasswordNeverExpires $false

5. Leave your Windows PowerShell session open for future lab exercises; simply minimize it before going on to the next exercise. In addition, leave your browser and all its tabs open.

**Results**: After completing this exercise, you should have created new users, assigned licenses, modified existing users, and configured groups and Adatum's password policies, and reset a user password by using the Windows PowerShell command-line interface.

# Proceed to Lab 2 - Exercise 5

