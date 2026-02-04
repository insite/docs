# Message Placeholders

When creating the content for an Notification, Newsletter or Invitation, there are Placeholders that can be added in the content. Please see below a list of the Placeholders available and what information each Placeholder provides:

Please note Placeholders should not be used in **Alerts**, please [**contact**](mailto:support@shiftiq.com) your Shift iQ representative to assist with the initial setup.

### NOTIFICATION Placeholders:

* $RecipientFirstName - First Name of person receiving Newsletter
* $RecipientLastName - Last Name of person receiving Newsletter
* $RecipientEmail - Email address of person receiving Newsletter
* $RecipientPersonCode - Person Code of person receiving Newsletter
* $Social-Media-Links - Display Organization's social media links (Please [**contact**](mailto:support@shiftiq.com) your Shift iQ representative to assist with the initial setup) ![placeholders.png](https://e02.insite.com/files/sites/global/message-placeholders/placeholders.png)
* $Unsubscribe-Link

<br>

**Message Variables (For Survey Workflow Notifications ONLY):**

* $UserFullName - First and Last Name of person who triggered the Notification
  * An link in the notification to the Contact Record of the user who submitted the survey response, so that an administrator can go directly to the user's Contact Record.
    * Add **$UserFullName** in square brackets **\[$UserFullName]** followed by the **/ui/admin/contacts/people/edit?contact=$UserIdentifier** URL in parentheses **(/ui/admin/contacts/people/edit?contact=$UserIdentifier)**\
      ![placeholders-3.png](https://e02.insite.com/files/sites/global/message-placeholders/placeholders-3.png)
* $UserEmail - Email of person who triggered the Notification
* $SurveyFormName - Survey that triggered the Notification

**Message Variables (For Gradebook Worklfow Notifications ONLY):**

* $CourseName
* $CourseStarted
* $LearnerFirstName
* $LearnerLastName

**Message Variables (For Course Completed Notifications ONLY):**

* $AppUrl
* $CourseName
* $CourseStarted
* $LearnerIdentifie
* $LearnerFirstName
* $LearnerLastName

**Message Variables (For Course Stalled Notifications ONLY):**

* $AppUrl
* $CourseName
* $CourseStarted
* $LearnerIdentifie
* $LearnerFirstName
* $LearnerLastName

**Message Variables (For Group Membership Notifications ONLY):**

* $GroupIdentifier
* $GroupName
* $UserIdentifier
* $UserName
* $UserEmail
* $AppUrl (link to the Shift iQ log in page)
* $EditPersonUrl (link to the contact record)
* $Reason (started or ended membership)

{Sender-Logo} and {Social-Media-Links} - These Placeholders do not work in Survey Workflow Notifications if attached to **Response Started (Administrator)**.<br>

### NEWSLETTER Placeholders:

* $RecipientFirstName - First Name of person receiving Newsletter
* $RecipientLastName - Last Name of person receiving Newsletter
* $RecipientEmail - Email address of person receiving Newsletter
* $RecipientPersonCode - Person Code of person receiving Newsletter
* $Social-Media-Links - Display Organization's social media links (Please [**contact**](mailto:support@shiftiq.com) your Shift iQ representative to assist with the initial setup) ![placeholders.png](https://e02.insite.com/files/sites/global/message-placeholders/placeholders.png)
* $Unsubscribe-Link



### INVITATION Placeholders:

* $RecipientFirstName - First Name of person receiving Newsletter
* $RecipientLastName - Last Name of person receiving Newsletter
* $RecipientEmail - Email address of person receiving Newsletter
* $RecipientPersonCode - Person Code of person receiving Newsletter
* $Social-Media-Links - Display Organization's social media links (Please [**contact**](mailto:support@shiftiq.com) your Shift iQ representative to assist with the initial setup) ![placeholders.png](https://e02.insite.com/files/sites/global/message-placeholders/placeholders.png)
* $Unsubscribe-Link
