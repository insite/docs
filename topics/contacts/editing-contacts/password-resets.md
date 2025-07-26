# Password Resets

## There are 2 methods of resetting a user's password:
<br>

**Method 1 - User resets their own**
Users can also reset their own passwords by clicking the **Reset my password** button on the initial login window. The system will ask them to enter the email address associated with their account and click **Continue**. It will then send them a link to a **Reset Password** screen where they can set their own new password.
<br>

**Method 2 - Admin resets Password on behalf of user**
From the Admin Home page, search for the user you would like to reset the password for ([**Searching Contacts**](/ui/help/portal/contacts/searching-contacts)). 

Select the **System Access** tab and under the **Sign In** tab click on the **Reset Password** button (on the top right of the card). The **Reset Password** dialogue box will appear with a system generated password; you can accept this OR overwrite both fields with one you've created. Click on **Save** in the **Reset Password** dialogue box.

Next click on the **Send Email** button and select **Welcome**. On the **Send Email** screen, select the **Shift iQ Alerts (Mailgun)** sender and review the information in the content field. You are able to make changes to the content if needed, then click the **Next** button. You will be redirected to the **Confirm** screen to review the message that will be sent to the user. Click **Confirm** to send the message.

The Welcome Email will include the user's **Login Name (Email)**, new **Temporary Password** and **Login** link. The user will be prompted to change the password on the first login.

Exit out of the contact record without saving; by doing so the system will reset the password expiry date for the record to the current date and time, which is what forces the user to change their **Temporary Password** upon logging in. 

![reset-password.png](https://e02.insite.com/files/sites/global/9856/reset-password.png)

***Note:*** There may be some situations where you don't wish to have the password expire when resetting it (i.e., test users); in this case you can set a desired expiry date and then save the contact record. Be aware that for unexpired passwords, the user will not be prompted to change it when logging in.

##### Passwords must have a minimum of 8 characters, use at least one uppercase letter, one lower case letter, one number and one symbol.
