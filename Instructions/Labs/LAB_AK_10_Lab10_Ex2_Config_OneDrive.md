# Module 10 - Lab 10 - Exercise 2 - Configuring OneDrive for Business

Now that she has implemented Microsoft Yammer in Adatum's Microsoft 365 pilot project, Holly Dickson is ready to do the same with Microsoft OneDrive for Business. Holly knows that with OneDrive, Adatum's users can easily and securely store and access their files from all their devices. This will enable them to more efficiently work with others regardless of whether they're inside or outside the organization and terminate that sharing whenever they want. 

Holly also knows that OneDrive for Business will help protect their work through advanced encryption while the data is in transit and at rest in data centers. Because Adatum is serious about improving its security requirements, Holly plans to implement OneDrive to help ensure that her users adhere to Adatum's most rigorous compliance standards by enabling them to choose where their data lives and providing detailed reporting of how that data has been changed and accessed. 

In this exercise, Holly will enable OneDrive for Business synchronization, create test files to be synchronized, and then verify file synchronization.

This lab exercise will be performed within LON-CL2.

## Task 1: Enable OneDrive for Business synchronization

1. On **LON-CL2**, you should still be logged in as the **Administrator**.

2. If Microsoft Edge is open from an earlier lab, then close it now. 

3. In an earlier lab, you logged into Microsoft 365 as Alan Yoo and you downloaded and installed **Microsoft 365 Apps for enterprise**. <br/>

	You should now open your local **Word** app again by selecting the **Windows** icon on the bottom-left corner of the taskbar, and then in the **Start** menu, selecting **Word**.

4. When **Word** opens, verify which user account it is licensed to at the top of the Word document. If Alan's name appears along with his initials in a circle, then skip to the next step. <br/>

	However, if a different user account appears, then select the user account, and in the window that appears, select **Sign in with a different account**.    In the **Sign in** window, enter **alan@M365xZZZZZZ.onmicrosoft.com (where ZZZZZZ is the unique tenant ID provided by your lab hosting provider) and a password of **Pa55w.rd**. Verify that **Alan Yoo** now appears at the top of the Word form. 

5. Now that you have verified that Word is licensed to Alan Yoo, close Word.

6. Open Microsoft Edge and then connect to **https://portal.office.com**.

7. Sign in as **Alan@M365xZZZZZZ.onmicrosoft.com** with a password of **Pa55w.rd**.

8. On the **Microsoft Office Home** page, select **OneDrive**.

9. If the **Welcome to OneDrive for Business** page appears, Select **Next**.

10. In the **OneDrive** window, select **+New** at the top of the page, and then in the drop-down menu that appears, select **Word document**. 

11. If a **Your privacy option** window appears, select **Close**.

12. In the **Word Online** tab that opens in your Edge browser, type some text, at which point Word Online will save the document as **Document.docx**. 

13. You want to rename the document as **OneDrive Test**, so in the Word menu bar, select **File**, select **Save as**, and then select **Rename**. In the window that appears, enter **OneDrive Test** in the **File Name** field and then select off this field. This will change the file name and close the window. 

14. Close the Word Online tab in your browser. 

15. In the **OneDrive** window, the **OneDrive test.docx** file should now appear in the list of files. On the menu bar at the top of the page, select **Sync**.

16. In the **This site is trying to open Microsoft OneDrive** window, select the **Always allow m365xZZZZZZ-my.sharepoint.com to open links of this type in the associated app** check box and then select **Open**.

17. In the **Set up OneDrive** window, Alan Yoo's account is displayed in the username field. Select **Sign in**.

18. In the **Enter password** window, enter **Pa55w.rd** and then select **Sign in**.

19. In the **Your OneDrive folder**, note the location of your OneDrive folder and then select **Next**. 

20. On the **Sync your files to this PC** window, select **Next**.

21. On the **Get to know your OneDrive** window, select **Next**.

22. On the **Share files and folders** window, select **Next**.

23. On the **Get the mobile app** window, select **Later**.

24. On the **You OneDrive is ready for you** window, select **Open my OneDrive folder**.

25. **File Explorer** is automatically opened for you. In the **File Explorer** window, select **OneDrive - Adatum Corporation**. 

26. Note that File Explorer displays the location where the synchronized files will be stored. Verify that the **OneDrive test.docx** file that you created earlier in Word Online has been synchronized to the local computer.

27. Leave File Explorer open as well as your Edge browser and proceed to the next task. 

## Task 2: Create files to synchronize with OneDrive for Business

Now that you have enabled file synchronization with OneDrive for Business, Holly Dickson wants to create test files to be synchronized and then verify file synchronization. 

1. On **LON-CL2**, ensure that the **OneDrive for Business** folder is open in File Explorer from the previous task. If not, open **File Explorer** and select **OneDrive - Adatum Corporation**. 

2. In **File Explorer**, select **Home** that appears in the menu bar at the top of the window. 

3. In the ribbon that appears on the **Home** tab, select **New folder**. This creates a new folder. Enter **Private** as the folder name.

4. You now want to create another folder, so select the **Home** tab again, and on the ribbon, select **New folder**, and then enter **Project A** as the folder name.

5. You now want to create a new Word document in the **Private** folder. <br/>

	If you double-click on the **Private** folder and then right-click in the detail pane and select **New** in the menu, it does NOT provide an option to create a Microsoft Word document. <br/>

	Instead, in the folder tree in the left-hand pane of the File Explorer window, you must select **OneDrive - Adatum Corporation** to expand it, then select the **Private** folder, right-click in the detail pane, and then select **New** in the menu. This will display a sub-menu with a variety of file types. Select **Microsoft Word Document** and name the document **Holidays.docx**.

6. In the **File Explorer** window, note the document icon that appears to the left of the **Holidays.docx**. It may be hard to see, but the icon is an image of two blue arrows. This will come into play after you complete this step. <br/>

	Double-click the **Holidays.docx** to open it (note Alan Yoo is the licensed user displayed in the top left-corner of the Word document). Type some text in the document, save the document, and then close Microsoft Word.

7. Note how the document icon for **Holidays.docx** changes from two blue arrows to a small green check mark icon after the synchronization process is complete. The document has been transferred to the OneDrive cloud storage automatically.

8. In the **File Explorer** window, navigate to **OneDrive for Business** in the navigation address line to move one level up.

9. In the **File Explorer** window, with the **OneDrive - Adatum Corporation** object expanded in the folder tree, select the **Project A** folder. Right-click in the detail pane for this folder, and in the menu that appears, select **New**, and then select **Microsoft Word Document**. Name the document **Project targets.docx**.

10. Double-click **Project targets.docx** to open it, and then type some short text, save the changes, and then close Microsoft Word.

11. Verify that the document synchronized by checking the document icon in File Explorer. The icon should be a green check mark. 

12. Minimize the **File Explorer** window.

13. To view the files online, switch to the Microsoft Edge window. You should still be in the **OneDrive** tab. Refresh the view.

14. In the **Files** list, you should see your two folders - **Private** and **Project A**.

15. Select the **Private** folder, and then select the **Holidays.docx** file to open it in Word Online.

16. In the menu bar at the top of the page, the **Tell me what you want to do** option is set to **Editing**. Add some additional text to the document. The document is saved automatically when **Saved** is displayed in the title bar.

17. In your Edge browser, select the **OneDrive for Business** tab.

18. Since you just updated the **Holidays.docx** file, you will see this reflected in the **Modified** column, which shows that the document changed just a few seconds ago.

19. Switch back to **File Explorer**. 

20. In the folder tree, **OneDrive - Adatum Corporation** should still expanded. Select the **Private** folder and then open **Holidays.docx**. You should see the changes you made in Word Online are synchronized back automatically.  

21. Leave File Explorer open as well as your Edge browser and proceed to the next task. 

## Task 3: Share files with other users

1. On **LON-CL2**, ensure that the **OneDrive for Business** folder is open in File Explorer from the previous task. If not, open **File Explorer** and select **OneDrive - Adatum Corporation** to expand it so that you can see the **Private** and **Project A** folders. 

2. In **File Explorer**, in the folder tree under **OneDrive - Adatum Corporation**, right-click the **Project A** folder and select **View online**.

3. Microsoft Edge opens (if you receive a dialog box asking which app to use to open this folder, select Microsoft Edge). If you are prompted to sign in, then sign in as Alan Yoo (**alan@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your tenant ID)) and a password of **Pa55w.rd**.

4. In your Edge browser, a tab should open with Alan Yoo's **OneDrive for Business** account. The tab should be displaying Alan's **My Files**, and specifically the **Project A** folder. <br/>

	Hover your mouse to the left of the **Project Targets.docx** field and select the circle so that it displays a check mark. With the file selected, select **Share** that appears in the menu bar at the top of the page..

5. In the **Send link** window that appears, enter the following information: <br/>

	- Enter **MOD** in the **Enter a name or email address** field. This will return a list of users whose name starts with MOD. Select **MOD Administrator**. 
	- In the **Add another** field, enter **Patti**. In the list of users, select **Patti Fernandez**. 
	- In the **Add a message (optional)** field, enter **This is the latest information for Project A**.

6. Select **Send**. After the emails are created, close the **Link sent** window.

7. In the upper text box, type **MOD Administrator**.

8. Open a new InPrivate Microsoft Edge window, and then connect to **https://portal.office.com**. 

9. Sign in as **admin@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is the tenant ID) and copy and paste in the tenant password provided by your lab hosting provider.

10. In the **Microsoft Office Home** page, select **Outook**.

11. Select the message with the subject **Alan Yoo shared ""Project Targets" with you**. 

12. In the message box, select **Project Targets**. 

13. Verify the document opens, and then make some changes to it. The changes should be automatically saved, and the file name at the top of the document should display **Saved**. All modifications are stored online in the OneDrive for Business cloud storage. By default, SharePoint Online creates a new version when the document changes. This can be viewed by the owner in the version history. 

14. Close the InPrivate Microsoft Edge window. 

15. You now want to turn off sharing for this document. In the Microsoft Edge window, the **Project targets** document should still be selected. Note in the file list, the **Sharing** column indicates the file is **Shared**. <br/>

	Select the **Shared** status in the **Sharing** column. This will open a **Manage access** window. (Note - Nother way to open the **Manage access** window for this file is to select **Share** in the menu bar just as you did when you originally shared the file, and then select the ellipsis icon in the **Share** window, and then select **Manage access**). 

16. In the **Manage access** window, select **Stop sharing**. In the confirmation window that appears, select **Stop sharing** again.

17. Close the **Manage Access** window. Note in the file list how the value of the **Sharing** column for this file changed from **Shared** to **Private**.

18. On the **Microsoft Office Home** page, select the user icon (the circle with Alan Yoo's **AY** initials in it) in the upper right-hand corner, and in the **My account** window that appears, select **Sign out**. Once you are signed out, close all other tabs, and then close Microsoft Edge.  


**Results**: After completing this exercise, you should have configured Microsoft OneDrive for Adatum.

# Proceed to Lab 10 - Exercise 3


