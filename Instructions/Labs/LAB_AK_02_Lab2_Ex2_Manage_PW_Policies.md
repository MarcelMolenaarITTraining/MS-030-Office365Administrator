# Module 2 - Lab 2 - Exercise 2 - Managing Microsoft 365 password policies

In this exercise, you will continue in your role as Holly Dickson, Adatum's Enterprise Administrator. As part of Adatum's Microsoft 365 pilot project, Holly wants to explore Microsoft 365 password management functionality. She will begin by configuring a Microsoft 365 password policy that sets user passwords to expire after 90 days and receive an upcoming expiration notification 14 days prior to expiration. 

Since Adatum is also interested in implementing Multi-factor authentication (MFA), Holly has been tasked with introducing MFA in their pilot project. MFA is a security standard that provides a stepping stone for businesses to strengthen user integrity. Multi-factor authentication is turned On by default for a Microsoft 365 tenant; however, for the purposes of this lab, MFA has been turned Off to enable Microsoft 365 to function more efficiently in your virtual lab environment. Therefore, Holly will turn on MFA for her own personal account to verify its functionality, and then she will turn it back off. At the end of this exercise, you will disable MFA for Holly's account. This will save you from having to enter the second form of authentication when signing in as Holly in any of the remaining labs in this course.

**Important:** To implement MFA, you will need to use your mobile phone to receive a verification code so that you can enter it into your tenant as a second form of authentication. If you do not have a phone, you will have to skip this lab. If this is the case, notify your instructor, who can potentially partner you with another student to follow along through this lab.


### Task 1 - Configure the Microsoft 365 password policy

In this task, you will change Adatum's password policy that controls how often users must change their password. A good practice is to have your users change their passwords every 90 days with a warning of 14 days prior to the update, both of which are the default settings in Microsoft 365. However, for this lab exercise, you will change password expiration to occur every 14 days, with a 14 day notification. 

**Important** - You are making this change simply for testing purposes. Since all users' passwords will expire within 14 days, and with a notification window of 14 days, they will all be within the 14 day notification window. This will enable you to see what happens when a user falls within the 14 day window prior to his or her password expiring. In this task you will make this policy change; in the next task, you will test the ramifications of this change.

1. You should still be logged into the **LON-CL1** VM as the **Administrator** from the prior lab exercise. The **Microsoft 365 admin center** should still be open in the Edge browser, and you should be signed into Microsoft 365 as **Holly Dickson**. 

2. In the **Microsoft 365 admin center**, in the left-hand navigation pane, select **Settings** and then select **Org settings**.

3. In the **Org settings** window, the **Services** tab is displayed by default at the top of the page. Select the **Security & Privacy** tab located next to it. 

4. In the **Security & Privacy** page, select the **Password expiration policy** in the list of settings. 

5. In the **Password expiration policy** pane that appears, select the check box for **Set user passwords to expire after a number of days**. <br>

6. Enter **14** in the **Days before passwords expire** field. Leave the **Days before a user is notified about expiration** field set to 14. Select **Save changes**.

7. Verify that the **Changes saved** message appears at the top of the page and then select the X in the upper right corner of the pane to close it. 

8. Leave your browser and all its tabs open for the next task.

### Task 2: Validate the password policy

In this task, you will validate the change that you made in the prior task when you set the password expiration setting to 14 days. With a 14 day notification window, you should now be able to see what happens when a user's password is due to expire and you are within the notification window. 

1. You should still be logged into the **LON-CL1** VM as the **Administrator** from the prior lab exercise. 

2. To see the affect of the password policy change, first sign out of Microsoft 365 as Holly Dickson. On the **Microsoft 365 admin center** tab, select the **HD** icon in the upper right corner of the screen, and in the window that appears, select **Sign out**. 

3. Close your **Edge** browser and all the tabs to clear your cache. Once the browser is closed, select the **Edge** browser icon on the taskbar to re-open it.

4. In the Edge browser, enter the following URL in the address bar: **https://portal.office.com**.

5. In the **Pick an account** window that appears, you want to sign back in as Holly Dickson, so select **holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID). 

7. In the **Enter password** window, enter provided by your lab hosting provider and then select **Sign in**.

8. If the **Get your work done with Office 365** window appears, then select the X in the upper right-hand corner of the window to close it. 

9. On the upper-right side of the window, verify that a notification appears with the following information: **Time to change your password. Your password will expire in 13 days.** <br>

	**Note:** It may take a few minutes before the password change notification message appears. <br>

10. Now that you have verified that your revised password policy works since you received a notification message indicating you must change your password, you should reset the policy by setting the expiration days from 14 back to 90. <br>

	Since you just logged into Microsoft 365 as Holly Dickson, in the **Microsoft Office Home** page, select **Admin** to open the **Microsoft 365 admin center**.

11. In the **Microsoft 365 admin center**, in the left-hand navigation pane,  select **Show all**, then select **Settings**, and then select **Org settings**.

12. In the **Org settings** window, the **Services** tab is displayed by default at the top of the page. Select the **Security & Privacy** tab located next to it. 

13. In the **Security & Privacy** page, select the **Password expiration policy** in the list of settings. 

14. In the **Password expiration policy** pane that appears, select the check box for **Set user passwords to expire after a number of days**. <br>

15. Enter **90** in the **Days before passwords expire** field. Leave the **Days before a user is notified about expiration** field set to 14. Select **Save changes**.

16. Verify that the **Changes saved** message appears at the top of the page and then select the X in the upper right corner of the pane to close it. 

17. Leave your browser and all its tabs open for the next task. While you would normally close your browser and then re-open it to reset the password policy, you don't need to do it here. In the next task, you will enable Multi-factor Authentication, which will require you to close and then re-open your browser. There's no reason to close and re-open your browser now and then do it again in the next task. Simply proceed to the next task.


### Task 3 - Enable and Disable Multi-factor authentication

To test Multi-factor authentication (MFA), Holly Dickson wants to turn it on for her personal Microsoft 365 user account and test how it works. Once you have verified that you can connect to Microsoft 365 using MFA, you will disable MFA for Holly's account. This will save you from having to enter the second form of authentication when signing in as Holly in any of the remaining labs in this course.

**Important:** To implement MFA, you will need a mobile phone to receive a text message containing a verification code. You will then enter the code into the Office 365 sign-in process as a second form of authentication. 

If you do not have a mobile phone:

- You can still perform this task, but you will have to skips steps 8-17 that verify MFA by having you log out and then enter a second form of authentication when you log back in to Office 365. 
- If you are in a classroom training environment, it is recommended that you notify your instructor, who can then potentially partner you with another student who has a mobile phone so that you can either use the other student's phone or watch the other student sign in. 
- If you are performing this training on your own and you do not have a mobile phone, or if you are in a classroom environment but cannot partner with another student, you can perform the steps in this task other than the ones that actually verify MFA (steps 8-17). This still allows you to enable and then disable MFA to get the experience of performing those steps. 

This is the only task in this course that requires a mobile phone.

1. You should still be logged into the **LON-CL1** VM as the **Administrator**.

2. The **Microsoft 365 admin center** should still be open in the Edge browser from the prior task, and you should be signed into Microsoft 365 as **Holly Dickson**. 

3. To enable MFA for Holly Dickson's user account, you must first access the **Active users** list in the **Microsoft 365 admin center**. In the **Microsoft 365 admin center**, in the left-hand navigation pane, select **Users** and then select **Active users**.

4. In the **Active users** window, on the menu bar at the top of the user list, select **Multi-factor authentication**. This will open a **multi-factor authentication** window in a new tab in your browser.

5. In the **multi-factor authentication** window, the **users** tab is displayed by default. Note the MFA status for all existing user accounts is **Disabled**.<br>

	Select the check box for **Holly Dickson**, and in Holly's properties pane that appears on the right, select **Enable**.

6. On the **About enabling multi-factor auth** dialog box, select **enable multi-factor auth**. 

7. When the **Updates successful** dialog box appears, select **close**. In the list of users in the **multi-factor authentication** window, verify Holly's MFA Status has changed to **Enabled**. 

8. You must now sign out of Microsoft 365 as Holly, close your browser session (to clear cache), open a new session, and then log back into Microsoft 365 as Holly. During the log-in process, you will be required to enter a second form of authentication as per MFA. When Holly signs back in after having MFA enabled for her user account, she will be asked for the authentication information needed for MFA, such as her phone number and authentication options. In your role as Holly, you will enter your mobile phone number, and you will receive a text message containing a verification code that you must enter to validate the authentication. You will perform these steps in the remaining portion of this task.</br>

	You must begin by signing out of Microsoft 365 as Holly, so select the **HD** user icon in the upper right corner of the browser (on the **multi-factor authenication** window, it may display Holly's username instead of her initials) and in the **My account** pane, select **Sign out**. 

9. Once you are signed out, close the browser and all the browser tabs.

10. Select the **Edge** icon on your taskbar to open a new browser session, and then open the **Office 365 Home** page by entering the following URL in the address bar: **https://portal.office.com**

11. In the **Pick an Account** window, select **Holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is the tenant suffix ID provided by your lab hosting provider). In the **Enter password** window, enter **Pa55w.rd** and select **Sign in**.

12. Because MFA is enabled for Holly, a **More information required** window appears. Select **Next**.

13. In the **Keep your account secure** window, it indicates that you can either use the Microsoft Authenticator app for MFA, or you can use a phone. <br>

	For the purposes of this lab, you should use the **Phone** method so that you do not have to take time installing the Microsoft Authenticator app that you may not use again after this training class. Since the window displays the Microsoft Authenticator method by default, select the **I want to set up a different method** option at the bottom of the window. 

14. In the **Choose a different method** dialog box that appears, select the drop-down arrow in the **Which method would you like to use** field and select **Phone**. Select **Confirm**.

15. In the **Keep your account secure** window, the **Microsoft Authenticator** section has now been replaced by a **Phone** section. Select your country or region from the drop-down list, enter your mobile phone number (**xxx-xxx-xxxx**), and then select **Next**.<br>

	**Note:** If you receive a message indicating that an error occurred, you should close the browser (closing all tabs) and then repeat steps 10-15. 

16. You will receive a text message on your mobile phone with a verification code to test whether the phone number you entered is correct. In the **Enter code** window that appears, enter the code that was sent in the text message and then select **Verify**.<br>

	**Note:** If you take too long to complete this process, the **Enter password** window will appear with a message indicating you took too long to complete the sign in process, so you will be timed-out. If this occurs, you must sign in again with Holly's password of **Pa55w.rd**. Another verification code will be texted to your phone, so enter it in the **Enter code** screen that appears and select **Verify**.

17. If a **Stay signed in?** window appears, select **Don't show this again** and then select **Yes**.

18. The **Office 365 Home** page should now be displayed in your browser. While Adatum will institute MFA once it eventually goes live with Microsoft 365 in its production environment, for now Holly wants to turn MFA off for her account for the remainder of the pilot project. She has just verified that she can use MFA to sign into Microsoft 365, so she will turn it off through the remainder of the pilot. <br>

	To disable MFA for Holly Dickson's user account, select **Admin** on the **Office 365 home** page to open the **Microsoft 365 admin center**. In the left-hand navigation pane, select **Users** and then **Active users**.

19. In the **Active users** window, on the menu bar at the top of the user list, select **Multi-factor authentication**.

20. In the **multi-factor authentication** window, the **users** tab is displayed by default. Note the MFA status for all existing user accounts is **Disabled**, except for Holly's account, which displays a status of **Enforced**. <br>

	**Note:** When you originally enabled MFA for Holly, the status was changed from **Disabled** to **Enabled**. However, now that Holly has signed in using MFA, her the status has changed from **Enabled** to **Enforced**.<br>

	Select the check box for **Holly Dickson**, and in Holly's properties pane on the right, select **Disable**.
21. On the **Disable multi-factor authentication?** dialog box, select **yes**. 

22. When the **Updates successful** dialog box appears, select **close**. In the **multi-factor authentication** window, verify Holly's MFA Status has changed to **Disabled**. 

23. You must now sign out of Microsoft 365 as Holly, close your browser session (to clear your cache), open a new session, and then log back into the **Office 365 home** page as Holly (**Holly@M365xZZZZZZ.onmicrosoft.com**). You should be familiar with these processes, so perform them now. <br>

	**Note:** with MFA turned off for Holly's account, you will simply need to enter Holly's password of **Pa55w.rd** when she logs in. Once you are logged in, you should then navigate to the **Microsoft 365 admin center**. 

24. After having completed the prior step, you should be logged into Microsoft 365 as Holly, and you should have the **Microsoft Office Home** page and the **Microsoft 365 admin center** open in your browser. Leave the browser and these tabs open and proceed to the next lab exercise.



**Results**: After completing this exercise, you should have configured and validated an Microsoft 365 password policy, including MFA.


# Proceed to Lab 2 - Exercise 3