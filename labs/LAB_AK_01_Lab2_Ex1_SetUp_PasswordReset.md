# Module 1 - Lab 2 - Exercise 1 - Configure Self-service password reset (SSPR) for user accounts in Azure AD


### Scenario

The Help Desk has indicated that a large number of support tickets are related to password resets. You have been asked to setup a way for users to reset their password on their own. 



#### Task 1: self-service password reset

1.  Switch to **LON-CL1** and sign in as **Adatum\\Administrator** with the password **Pa55w.rd**.

2.  On the task bar select **Microsoft Edge**, open Azure by going to (https:/portal.azure.com).  Login as Holly Dickson from the previous lab. Navigate to **Azure Active Directory**
    

3.  In the navigation pane under **Manage** select **Users**, then select **Password reset**.

4.  In the **Password reset | Properties** window, select **All** to enable self-service password reset to all users. Select **Save**.

5.  On the **Password reset | Properties** blade, select **Authentication methods**.

6.  For the methods available to users, ensure that **Mobile Phone (SMS only)** and
    **Email** are selected, and then select **Security Questions**.

7.  For the **Number of questions required to register**, select **3**.

8.  For the **Number of questions required to reset**, select **3**.

9.  In the **Select security questions** section, select **No security questions configured**, then select **Predefined**. Select three questions of your choice, and then select **OK** twice.

10. Select **Save**.

11. Select **Registration** Select **No** for **Require users to register when signing in**, and the select **Save**.


#### Task 2: Test self-service password reset

1.   In Microsoft Edge at the upper right of the page, select your account name, and then select
    **Sign in with a different account**. 

2.  Sign in as **AllanD@yourtenant.onmicrosoft.com** with the password that was assigned by your lab hosting service.   

3.  Browse to **https://myapps.microsoft.com**. 

4.  On the **Microsoft** page, select on the **Allan** account in the top right corner, and then select **Profile**.

5.  Select **Set up self service password reset**.

6.  On the **confirm your current password** page, if it appears, select **re-enter my password**, enter the password assigned by your lab hoster and select **Sign in**.

7.  On the **don’t lose access to your account** page, select **Set it up now** for the **Authentication Phone** option.

8.  Choose your **country or region**, type your **mobile phone number**, and then select **text me**.

9.  Type the number that you receive in a text message in the text box below, and then select **verify**.

10. Select **Set it up now** for the **Authentication Email** option. Type your email address that you easily access. Select **email me**.

    _Note: you will need to use an e-mail address other than the tenant domain 
    provided for this lab. If one is not available, you can skip the e-mail 
    verification and continue with the next step._

9. Sign in to your email account, read the code, type it in the verification field, and then select **Verify**. 
    
    _Note: If you don’t find a message with a code in your inbox, check the junk folder._

10. On the line for **Security Questions are not setup**, select **Set it up now**. Choose the three security questions and enter in any answer. Select **Save answers**.

11. On the **don’t lose access to your account!** page, select **Finish**.

12. On the **Microsoft** page, select on the **Allan** account, and then select **Profile**.

13. In the portal, select **Change password**.

14. On the **change password** page, in the **Old password** text box, type Allan's password assigned by your lab hoster, in the **Create new password** and the **Confirm new password** text boxes, type **Pa55w.rd** and then select **Submit**.

15. Wait until the Microsoft Azure profile portal appears, and then close the Microsoft Edge browser window.

# Continue to Exercise 2

