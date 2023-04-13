# Module 6 - Lab 6 - Exercise 1 - Managing Exchange Online recipients

As part of its Microsoft 365 deployment, Adatum wants to implement Exchange Online. As part of Adatum's pilot project, Holly Dickson, Adatum's Enterprise Admin, wants to investigate three key features related to mail flow recipients within Exchange Online - user mailboxes, groups, and contacts. 

Holly will begin by creating user accounts and mailboxes in Exchange Online. She will then create two types of groups within Exchange Online. The first will be a distribution list of email recipients, which is used to create a one-stop email list for contacting users simultaneously rather than having to email each recipient individually. The second type of group is a Microsoft 365 group.

One of the key features of Exchange Online is the ability to maintain different types of contacts in the Exchange Admin Center. Holly will complete this exercise by implementing mail contacts and mail users.

### Task 1 – Manage Recipients

As you continue in your role as Holly Dickson, you are ready to review the steps involved in creating and managing mail flow recipients in Exchange Online.

1. Switch to LON-CL1, where you should still be logged in as the **Administrator** with a password of **Pa55w.rd**.

2. You should still have **Microsoft Edge** open and the **Microsoft 365 admin center** open from the prior lab. If so, proceed to the next step; otherwise, open Edge, navigate to **https://portal.office.com/**, log in as **Holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is the tenant ID provided by your lab hosting provider) and **Pa55w.rd**, and then in the **Microsoft Office Home** page, select **Admin** to open the Microsoft 365 admin center.

3. In the **Microsoft 365 admin center**, in the left-hand navigation pane, select **Show all** (if necessary), then scroll down to **Admin centers** and select **Exchange**. This will open the **Exchange admin center** for Exchange Online.

4. In the **Exchange admin center,** select **recipients** in the left-hand navigation pane.

5. In the **recipients** view, the **mailboxes** tab appears by default (see the tabs at the top of the page). The mailboxes that appear in this view include all the user accounts that were pre-created in your tenant by the lab hosting provider, along with mailboxes for users that you created in Lab 2 that were assigned an Office 365 license (Holly, Ada Russell, Alan Yoo, Catherine Richard, and Tameka Reed). Note the users that you created in the earlier lab that were not assigned a license (such as Adam Hobbs) do not have an Exchange Online mailbox. <br/>

	Select the mailbox for **Joni Sherman** by double-clicking on her **DISPLAY NAME.** This will open the **Edit Mailbox** window with Joni’s data prefilled. By default, the window displays the **general** tab (the tabs appear in the left-hand pane).

6.  The **general** tab in the left-hand navigation pane is displayed by default. At the bottom of the **general** tab, select **More options**.

7. Under **Custom attributes**, select the **pencil (edit)** icon. 

8. This opens the **Custom attributes** window for Joni. You can enter up to 15 attributes. You will not be entering any attributes in this lab exercise, but it’s important that you know this feature is available. Select **Cancel**.   <br/>

	‎**Note:** Custom attributes are properties your company can use for specific mailbox identification, such as a cost center number for the mailbox or other information such as an HR personnel number.

9. In addition to the **general** tab, the left-hand pane of the **Edit Mailbox** window includes several other tabs that enable you to enter additional information pertaining to this specific mailbox. While you will not enter any of this optional information for the purposes of this lab, take a few minutes now and select the following tabs to see what information can be captured: 

	- **contact information.** This tab enables you to add personal information such as Street, City or Mobile number for the user.

	- **organization.** This tab enables you to add company-specific information such as Title or Department for the user.

	- **mailbox features.** This tab enables the admin to assign specific policies to the user. These policies range from the sharing policy to the address book policy. This option also covers device usage and connectivity.

	- **member of.** This tab displays the Distribution groups that include this user.
	
10. On the left-hand pane select **mailbox delegation.** This option allows the admin to assign a user to this mailbox’s Send As, Send on Behalf, or Full Access permissions. This option is commonly used if you want another user to be able to send messages from this mailbox. <br/>

	Scroll down on this **mailbox delegation** window and select the plus (+) sign under the **Full Access** section. 

11. In the **Select Full Access** window select **Holly Dickson**, select the **add-&gt;** button, and then select **OK.**  <br/>

	‎**Note:** After about an hour Holly Dickson will be able to access Joni’s mailbox without needing a password.

12. On Joni Sherman's **Edit Mailbox** window, select **Save**, and then select **OK** once the changes are saved.

13. Leave your browser and all the tabs open for the next task.

 
### Task 2 – Manage Groups 

In this task you will create two types of groups within Exchange Online. The first is a distribution list of email recipients, which is used to create a one-stop email list for contacting users simultaneously rather than having to email each recipient individually. The second type of group is an Office 365 group.

1. You should still be in LON-CL1 and your browser should still be open to the **Exchange admin center** from the prior task, where it should still be displaying **recipients** from the left-hand navigation pane. In the prior task, you worked with user accounts using the **mailboxes** tab. In this task, you will be creating groups, so select the **groups** tab at the top of the **recipients**’ page.  <br/>

	**Note:** You should see the Inside Sales and Manufacturing groups that you created in earlier labs.  

2.	Select the drop-down arrow next to the **New Microsoft 365 group** button. In the drop-down menu, select **Distribution list**.

3. In the **new distribution list** window that appears, enter the following information:

	- Display Name: **Sales Department**

	- Alias: **SalesDept**

	- Email Address: tab into the field and the **SalesDept** alias will appear. In the domain field to the right of it, select the drop-down arrow and select **M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider).

	- Owners: Since you are logged into the EAC using Holly Dickson, her account is displayed as the default Owner. However, Holly wants Alex Wilber to co-own the group, so select the **plus (+)** sign under the **Owners** section, and in the **Select Owner** window, select **Alex Wilber**, select the **add-&gt;** button, and then select **OK**.

	- Members: select the plus (+) sign under the **Members** section, and in the **Select Members** window, select **Allan Deyoung**. Then hold down the **Ctrl** key and select **Diego Siciliani** and **Lynne Robbins**. This will select all three users at once, at which point you should select the **add-&gt;** button and then select **OK**. 

4. Select **Save** and then select **OK** once the changes are saved successfully.

5. Select the **+New Office 365 group** button (not the drop-down arrow to the right of it, but the button itself). 

6. In the **Create a group** window that appears, enter the following information:

	- Group name: **Dynamics CRM Project Team**

	- Group email address: **DynCRM**

	- Group email address domain: In the domain field to the right of the **DynCRM** alias, select the drop-down arrow and select **M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider)

	- Privacy: **Public – Anyone can see content**

	- Owners: Leave as **Holly**

	- Language: Leave as **English**

	- Description: **Group of all company employees working on the Microsoft Dynamics CRM project.**

	- Subscribe new members: leave this check box selected so that members get conversations and calendar events sent to their Inboxes

7. Select **Save** and then select **OK** once the changes are saved successfully.

8. In the **Dynamics CRM Project Team** window that appears, you will now perform maintenance on this existing group. The **ownership** tab in the left-hand pane is displayed by default. Under **Owners**, select the **plus (+)** sign, and in the **Select Members** window, select **Nestor Wilke**, select the **add-&gt;** button, and then select **OK**.

9. In the left-hand pane, select **membership**.

10. Under **Members**, select the **plus (+)** sign, and in the **Select Members** window, select **Isaiah Langer**. Then hold down the **Ctrl** key and select **Joni Sherman**, and **Patti Fernandez**. This process will select all three users. Select the **add-&gt;** button and then select **OK.** 

11. Select **Save** and then select **OK** once the changes are saved successfully.

12. Leave your browser and all the tabs open for the next task.

### Task 3 – Manage Resources

A room mailbox is a resource mailbox that is assigned to a physical location, such as a conference room, an auditorium, or a training room. Users can easily reserve these rooms by including room mailboxes in their meeting requests. Adatum’s CTO wants to test this feature using the company’s most popular conference room, and he has asked Holly to configure this resource.

1. You should still be in LON-CL1 and your browser should still be open to the **Exchange admin center** from the prior task, where it should still be displaying **recipients** from the left-hand navigation pane, and on the **recipients** page, it should be displaying the **groups** tab. In the prior tasks you managed mailbox and group recipients; in this task, you will manage resource recipients. <br/>

	On the **recipients** page, select the **resources** tab at the top of the page.

2. In the menu bar that appears over the list of resources, select the **plus (+)** sign and then in the drop-down menu, select **Room mailbox.**  <br/>
	
	‎**Note:** This selection is designed for administrators to set up a meeting location to be used for booking purposes. When scheduling meetings, you will be able to select the room from the Global Address List (GAL).

3. In the **new room mailbox** window that appears, enter the following information:

	- Room name: **Conference Room 1**

	- Email address: **Con1**

	- Email address domain: In the domain field to the right of the **Con1** alias, select the drop-down arrow and select **M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider)

	- Location: The room is in Building 5, Room 2011, so enter **5/2011**

	- Phone: **425-555-2011**

	- Capacity: **15**

4. Select **Save** and then select **OK** once the changes are successfully saved.

5. **Conference Room 1** now appears in the list of resources. You must now edit the booking properties for this resource. Since Conference Room 1 is the only resource in the list, it's already selected by default; therefore, select the **Edit** (pencil) icon on the menu bar.

6. In the **Conference Room 1** window that appears, select **booking options** in the left-hand pane.

7. Select the **Allow scheduling only during working hours** check box. 

8. In the **Maximum booking lead time (days)** field, change the value from **180** days to **60** days.  <br/>

	‎**Note:** The standard duration of 180 days can be too long for scheduling out most meetings. As a best practice, organizations should establish a company standard so that events do not over-book locations.

9. In the **Maximum duration (hours)** field, change the value from **24.0** hours to **120** hours (this is five days, or one work week). 

10. In the left-hand navigation pane, select **booking delegates**.

11. Select the **Select delegates who can accept or decline booking requests** option.  <br/>

	**Note:** This option allows a user to filter booking requests.

12. Under **Delegates**, select the **plus (+)** sign. In the **Select Delegates** window, select **Holly Dickson** and then hold down the **Ctrl** key and select and **Nestor Wilke**. This will select both users at once; then select the **add-&gt;** button and select **OK.** 

13. Select **Save** and then select **OK** once the changes are successfully saved.

14. Leave your browser and all the tabs open for the next task.

### Task 4 – Manage Contacts

One of the key features of Exchange Online is the ability to maintain different types of contacts in the Exchange Admin Center. In this task, you will be introduced to mail contacts and mail users.

1. You should still be in LON-CL1 and your browser should still be open to the **Exchange admin center** from the prior task, where it should still be displaying **recipients** from the left-hand navigation pane. In this list of recipient tabs across the top of the screen, select **contacts.**

2. In the menu bar that appears over the list of contacts, select the **plus (+)** sign, and in the menu that appears, select **Mail contact.**  <br/>

	‎**Note:** This option enables external people from outside your organization to be added to your Exchange Online distribution lists.

3. In the **new mail contact** window that appears, enter the following information.

	- First name: **Bao**

	- Initials: leave blank

	- Last Name: **Chu**

	- Display Name: tab into the field and **Bao Chu** is automatically displayed

	- Alias: **Hai**

	- External Email Address: **Hai@fabrikam.com**

4. Select **Save** and then select **OK** once the changes are successfully saved. Hai should now appear in the list of contacts as a **Mail contact**.

5. On the menu bar above the contacts list, select the **plus** **(+)** sign to add another contact. In the drop-down menu, select **Mail user.**  <br/>

	**Note:** This option is for individuals who need to use the company domain even though they are not a full-time employee (for example: contractors, advisors, and selective temporary staff). This option will forward email to the individual’s external email when mail is sent to the contact’s internal company account.  <br/>
	
	‎**WARNING**: A Mail User does not need a license to access SharePoint Online; the user simply needs to be given access to it.   
	
6. In the **new mail user** window that appears, enter the following information:

	- First name: **Albert**

	- Initials: leave blank

	- Last Name: **Eksteen**

	- Display Name: tab into the field and **Albert Eksteen** is automatically displayed

	- Alias: **Albert**

	- External email address: **Albert@fabrikam.com**

	- User ID: **v-Albert** (this is the user’s alias for his internal Adatum account)

	- User ID domain: in the domain field to the right of the User ID, select the drop-down arrow and select **M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider)

	- New password: **Pa55w.rd**

	- Confirm Password: **Pa55w.rd**

7. Select **Save** and then select **OK** once the changes are successfully saved. Bill should now appear in the list of contacts as a **Mail user**.

8. In your Edge browser session, leave all the tabs open, including the Exchange admin center; these will be used in the next lab exercise.

# Proceed to Lab 6 - Exercise 2
