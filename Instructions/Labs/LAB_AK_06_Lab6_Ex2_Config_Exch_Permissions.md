# Module 6 - Lab 6 - Exercise 2 - Configuring Exchange Online permissions

In this exercise you will continue in your role as Holly Dickson, Adatum’s Enterprise Administrator. Holly has been tasked with managing admin roles and permission policies for Adatum. The CTO has asked Holly to create a new management role group that allows an administrator to remotely access a mailbox without having the password. 

In the prior lab exercise, you maintained Exchange Online recipients from the Exchange Admin Center. In this exercise, you will use Windows PowerShell to create a new Exchange role, assign members to it, and create a new role assignment policy. This will provide you with experience using both the online admin center and PowerShell to manage Exchange recipients and permissions.  

### Task 1 Create a new admin role and assign a user to it

In this task you will configure Exchange admin roles through Windows PowerShell. Creating a new role such as this is useful when you want to limit the amount of control given to a person who will only be in an administrative role temporarily. 

1. You should still be logged into **LON-CL1** as the **Administrator** account with a password of **Pa55w.rd**.

2. Windows PowerShell should be open from an earlier lab exercise. However, if you closed it, then re-open an elevated instance of it (Run as administrator) now. 

3. In the **Windows PowerShell** window, at the command prompt type the following command and then press Enter to set the execution policy to remote signed, which requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher. <br/>

		Set-ExecutionPolicy RemoteSigned

	If you are prompted to verify that you want to change the execution policy, enter **A** to select **[A] Yes to All.**  

4. At the command prompt, enter the following command and then press Enter to install the Exchange Online Management Module into Windows PowerShell. <br/>

		Install-Module -Name ExchangeOnlineManagement

	If you are prompted to verify that you want to install the module from an untrusted repository, enter **A** to select **[A] Yes to All.**  

5. At the command prompt, enter the following command and then press Enter to prompt you for the sign-in credentials of the user who will be signing into Exchange Online. For each subsequent command that is run, these credentials will be verified to determine if the user has the permissions necessary to make the change. <br/>

		$UserCredential = Get-Credential

6. In the **Windows PowerShell credential request** window that appears, enter the credentials of Adatum's MOD Administrator. Enter **admin@M365xZZZZZZ.onmicrosoft.com** in the **User name** field (where ZZZZZZ is your tenant ID), enter the tenant password provided by your lab hosting partner in the **Password** field, and then select **OK**.   

7. At the command prompt, enter the following command and then press Enter to connect you to Exchange Online and sign in automatically with your stored credentials. <br/>

		Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true

8. At the command prompt, enter the following command and then press Enter. This command is specific to this task. Normally running the following commands would result in an unauthorized access error; however, this command enables you to run them. Note: This command is only for Exchange Online use. <br/>	
		
		Enable-OrganizationCustomization

9. At the command prompt, enter the following command and then press Enter to create a new role group called **BranchOfficeAdmins**, with the following roles assigned to it: **Mail Recipients**, **Distribution Groups**, **Move Mailboxes**, **Mail Recipient Creation**. <br/>

		New-RoleGroup -Name BranchOfficeAdmins -roles “Mail Recipients”, “Distribution Groups”, “Move Mailboxes”, “Mail Recipient Creation”

	**Note:** This command may take a few minutes to complete. 

10. At the command prompt, enter the following command and then press Enter to add Nestor Wilke to the Branch Office Admins role group: <br/>
		
		Add-RoleGroupMember "BranchOfficeAdmins" -Member 'Nestor Wilke'

11. At the command prompt, enter the following command and then press Enter to retrieve all members associated to Branch office admins role group (which, at this point, is only Nestor Wilke): <br>

		Get-RoleGroupMember "BranchOfficeAdmins"

12. Minimize the Windows PowerShell window.

13. You will now verify the changes that you made in PowerShell are visible in the Exchange admin center. Your Edge browser should be open from the prior task, with tabs open for the **Microsoft Office Home** page, the **Microsoft 365 admin center**, and the **Exchange admin center**. You should still be signed into Microsoft 365 as Holly Dickson. <br/>

	If you closed the Exchange admin center tab after the prior lab exercise, then in the **Microsoft 365 Admin center**, under **Admin Centers** in the left-hand navigation pane, select **Exchange**.

14. In the **Exchange admin center**, in the left-hand navigation pane, select **permissions**. 

15. On the **permissions** page, the **admin roles** tab is displayed by default. The **BranchOfficeAdmins** role group should appear in the list of admin roles. Select **BranchOfficeAdmins**. 

16. The detail pane for the **BranchOfficeAdmins** role group should appear to the right of the list. This detail pane displays all the roles assigned to this role group, as well as Nestor Wilke, who is the only member. 

17. Leave your browser and all tabs open.

### Task 2: Create a new role assignment policy

Exchange Online comes with a default user role policy titled **Default Role Assignment Policy**. This policy grand end users the permission to set their options in Outlook on the web and perform other self-administration tasks. 

Holly Dickson wants to add an additional role assignment policy and set it as the default policy for Adatum. In this task, she will use PowerShell to create the policy and set it as Adatum's new default policy.

1. At the end of the prior task, you were in **LON-CL1** in the **Exchange admin center**, and you displayed the **permissions** tab. On the **permissions** page, you had selected the **admin roles** tab. <br/>

	On the **permissions** page, you should now select **user roles**. Note that there is only one role, the **Default Role Assignment Policy**.  <br/>

	In this task, you are going to create a new role assignment policy, but instead of doing it through the Exchange admin center, you will do it through Windows PowerShell. Therefore, minimize your Edge browser. 

2. In the prior task, you minimized the Windows PowerShell console once you were done with PowerShell. Now that you will be using PowerShell again, select the **Windows PowerShell** icon on the taskbar. 

3. In the **Windows PowerShell** console, at the command prompt, enter the following command and then press Enter to create a new user role policy titled **Limited Mailbox Configuration**, with the following roles assigned to it: **MyBaseOptions**, **MyAddressInformation**, and **MyDisplayName**. <br/>

		New-RoleAssignmentPolicy "Limited Mailbox Configuration" -Roles MyBaseOptions,MyAddressInformation,MyDisplayName

4. At the command prompt, enter the following command and then press Enter to change the default role assignment policy for new mailboxes. This command will set the **"Limited Mailbox Configuration"** policy to be the new default Role assignment policy. <br/>

		Set-RoleAssignmentPolicy "Limited Mailbox Configuration" -IsDefault

	When prompted to confirm whether you set the Limited Mailbox Configuration policy as the default Role Assignment Policy, enter **A** to select **[A] Yes to All.**

5. Minimize the **Windows Powershell** console.

6. Select the **Edge** browser icon on the taskbar, and then select the **Exchange admin center** tab.

7. In the **Exchange admin center**, you should still be on the **permissions** page and displaying the **user roles** tab. In the menu bar that appears above the list of user roles, select the **Refresh** icon. You should now see the new **Limited Mailbox Configuration** role assignment policy that you created in PowerShell.

8. Leave your browser and all tabs open and proceed to the next lab.


**Results**: After completing this exercise, you will have configured delegated administration of your Exchange Online organization.


# End of Lab 6