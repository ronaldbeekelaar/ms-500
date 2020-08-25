# Module 5 - Lab 1 - Exercise 1 - Implement ATP Policies  

You have a Global Admin account set up for Holly Dickson, and you&#39;re signed into Microsoft 365 as Holly. In this phase of your pilot project for Adatum, you want to edit an existing ATP Safe Links policy, and then create a Safe Attachments policy and turn on Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams. You will also validate both policies to ensure they work properly.

### Task 1 – Create a Safe Links Policy

In this task, you will add the URL **tailspintoys.com** to the company-wide list of blocked URLs, and you will create an ATP safe links recipient policy that applies to all users in your tenant.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **lon-cl1\admin** account, and you should still be logged into Microsoft 365 as **Holly Dickson**.

2. You should still be in the Microsoft 365 Security and Compliance center. If not, in your browser, enter **https://protection.office.com.**

3. In the **Security &amp; Compliance center**, in the left navigation pane, select **Threat Management** and then select **Policy**.

4. In the **Policy** window, scroll to the right (if necessary) and select the **ATP Safe Links** tile.

5. In the **Safe Links** window, note that there are two sections of policies that can be created: **Policies that apply to the entire organization**, and below that, **Policies that apply to specific users.**

6. Under the **Policies that apply to the entire organization** section, there is only one policy in the list, which is the **Default** policy. Since this policy is already selected, select the **pencil (edit)** icon on the menu bar.

7. In the **Safe links policy for your organization** window, under the **Settings that apply to content across Office 365** section, you can enter any URLs that you want to have blocked. For this test lab, in the **Enter a valid URL** field, enter **http://tailspintoys.com** and then select the **plus (+)** sign to add it to the policy.

8. Select **Save**.  Click **OK**.

9. Scroll down to **Policies that apply to specific users** and select the **plus (+)** sign to add a new recipient policy.

10. Insert the following to the windows fields:

    - Name: **All company users**

    - Select the action for unknown potentially malicious URLs in messages: This is set to Off by default. Select **On – URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.

    - Check the **Apply safe links to email messages sent within the organization** check box.

    - In the **Applied To** section, below the **If…** condition, select the drop-down arrow in the **Select one** field, and then in the drop-down menu, select **The recipient domain is**.

    - In the pop-up window that appears, the available domain is **M365xZZZZZZ.onmicrosoft.com**. Select **add-&gt;** and then select **OK.**

11. Select **Save** and click **OK** to close the window.

12. Leave the Office 365 Security &amp; Compliance tab open for use in a later task.

### Task 2 – Validate the Safe Links Policy

In this task, you will test the Safe Links Policy that you just created that blocks links to the http://tailspintoys.com URL.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**.

2. In your **Microsoft Edge** browser, select the **Microsoft Office Home** (or go to https://office.com) tab and then select **Outlook.**

3. If you receive a **We updated Outlook** message, select **Not Now**, or if you see a **Welcome** message, then close it.

4. In **Outlook on the web**, select **New Message** in the upper left part of the screen.

5. In the right pane, enter the following email information:

    - To: You will be sending an email to the MOD Administrator, so enter **mod** in the **To** field and then select the **MOD Administrator** email address from the drop-down list.

    - Add a subject: **Free stuff from Microsoft**

    - Add a message: **Please click on me for free toys from Microsoft.**

6. Select the text that you added in the body of the message.

7. At the bottom of the detail pane, below the body of the message, is a taskbar. On the taskbar, select the **Insert hyperlink** icon to display the Insert link window.

9. In the **Insert link** window, the text that you highlighted in the body of the message should be displayed in the **Display as** field. In the **Web address (URL)** field, enter the following URL: **http://tailspintoys.com/aboutus/freetoys**.

10. Select **OK**.

11. In the body of the email, the message should still be selected. Click anywhere in the body of the message to remove the highlighting. The color of the text should now be blue and it should be underlined, indicating that this message is hyperlinked to a URL.

12. Select **Send** in the menu bar that appears above the message (or the **Send** button at the bottom of the page).

13. You now want to open the MOD Administrator&#39;s Inbox in Outlook and validate whether the ATP policy you created in the prior task worked on the email that you just sent from Holly.

    To do this, you must switch the Client 2 VM. In the **Virtual machine** field at the top of the page, select the Client 2 VM (LON-CL2).

14. Log into the VM as the **Admin** account by entering **Ps55w.rd** in the **Password** field if necessary.

15. Select the **Microsoft Edge** icon in the taskbar, maximize the window and then enter the following URL in the address bar: **https://outlook.office365.com**

16. Since you want to sign in as the MOD Administrator, in the **Sign-in** window, enter **admin@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your tenant ID provided by your lab hosting provider) and then select **Next**.

17. In the **Enter password** window, enter the password provided by your lab hosting provider and select **Sign in**.  If you are requested to provice self-service password information click **cancel**.

18. Close the **Let Microsoft Edge save and fill your password for this site next time?** banner by selecting **Never**.

19. On the **Stay signed in?** dialog box, select the **Don't show this again** check box and then select **Yes.**

20. Close the **Welcome** window that appears.

21. In the MOD Administrator&#39;s **Inbox**, open the email that was sent by Holly.

22. When you hover over the blue link that appears in the body of the email, you can see a long URL in the bottom of the browser window; this URL starts with **https://nam03.safelinks.protection.outlook.com**.

    When you select the hyperlink to open it, a new tab in **Edge** opens that displays the following warning message: **Opening this website might not be safe.** This message indicates that your ATP Safe Links policy is working correctly and access to the URL is blocked with ATP Safe Links.

23. Leave the Client 2 VM open and leave Outlook open to the MOD Administrator&#39;s Inbox for later.

### Task 3 – Create a Safe Attachment policy and turn on ATP for SharePoint, OneDrive, and Microsoft Teams

In this task, you will, and you&#39;ll create an ATP Safe Attachments policy that will test email attachments for malware that are sent to recipients within the M365xZZZZZZ.on microsoft.com domain. You will configure the policy so that if an attachment is blocked, it will be removed from the email that is sent to the recipient, and a copy of the email will be redirected to Joni Sherman for additional review.

1. Switch back to your Client 1 VM (LON-CL1). You should still be logged into your Client 1 VM as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**.

2. In your **Edge** browser, select the **Office 365 Security &amp; Compliance** tab.

3. In the **Office 365 Security &amp; Compliance center**, in the left navigation pane under **Threat Management**, select **Policy**.

4. In the **Policy** window, select the **ATP Safe Attachments** tile.

5. On the **Safe attachments** window, at the top of the page under the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section, select the **Turn on ATP for SharePoint, OneDrive and Microsoft Teams** checkbox.

6. Under the **Protect email attachments** section, select the **plus (+) sign** on the menu bar to add a new safe attachments policy.

7. In the new safe attachments policy window, enter **AttachmentPolicy1** in the **Name** field.

8. Under the **Safe attachments unknown malware response** section, select **Dynamic Delivery** (this option will still send the email but will hold the attachment until it has been scanned and marked acceptable).

9. Under the **Redirect attachment on detection** section, select **Enable redirect**.

10. In the **Send the attachment to the following email address** field, enter **JoniS@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider)

11. Scroll down in the window and under the **Applied To** section, under **If** (the first condition), select the drop-down arrow and select **The recipient domain is...**

12. In the **NAME** dialog box, select the **M365xZZZZZZ.onmicrosoft** domain (where ZZZZZZ is your tenant ID provided by your lab hosting provider), select **add->**, and then select **OK**.

13. On the **new safe attachments policy** window, select **Save**.

14. Two warning messages will be displayed regarding the **Dynamic Delivery** and **Enable redirect** options that were selected. Select **OK** for each.

15. It may take a minute or so to update the organization settings. In the **Update complete** window, select **OK**.

**NOTE:** Unfortunately, we are unable to create a training lab in which you can validate the ATP Safe Attachments policy that you just created. To do so, you must send an email that contains a malicious attachment. There are some common test viruses that are available, such as the EICAR test virus; however, with well-known test viruses such as EICAR, the messages in which they are attached get quarantined before they can be processed by Office 365 ATP. Since ATP Safe Attachments functionality is meant to protect against unknown and zero-day viruses and malware, it is very difficult, and not recommended, to create such an attachment.

That said, after you have defined your ATP Safe Attachment policies in your real-world environment, one  way to see how the service is working is by viewing Advanced Threat Protection reports. For more information on using ATP reporting to validate your Safe Links and Safe Attachment policies, see [View reports for Office 365 Advanced Threat Protection](https://docs.microsoft.com/en-us/office365/securitycompliance/view-reports-for-atp).


# End of Lab

