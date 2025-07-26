In the **Survey**, click on the **Messages** tab, then on the tab you wish to configure a workflow for: 

* **Response Started (Administrator):**  A notification is sent to an **Administrator** as soon as a user starts a Survey response.
* **Response Completed (Administrator):**  A notification is sent to an **Administrator** once a user submits their Survey response.
* **Response Completed (Respondent):**  A notification is sent to the **Respondent** after they submit their Survey response.

Click on the **Assign Messages** button to assign an **existing** notification or **Add Notification** to create a **new** notification.

**Assign Messages** button:
* Under the **Email Notifications** heading, select an existing notification for each of the above workflows. 

**Add Notification** button:
* Click on the **Add Notification** button.
* Add the **Internal Name** and **Subject**.
* Then select the **Save** button.
* After saving you will be redirected to the **Message Outline** page where you can modify the notification's content, under the **Content** tab.

**Placeholders** that work with **Survey Workflow Notifications**:
* **$UserFullName** - Full Name of person who starts/completes a response
* **$UserEmail** - Email of person who starts/completes a response
* **$SurveyFormName** - Internal name of the Survey that was started/completed
* [**$UserFullName**](https://**Your Org**.insite.com/ui/admin/contacts/people/edit?contact=$UserIdentifier) - use to create a hyperlink to the respondent's contact record (use on Administrator workflows only)
* [**Review Your Response**](https://**Your Org**.insite.com/ui/survey/respond/search) - use to create a hyperlink for the respondent to log in to their portal and see/review/resume all of their survey responses (use on Response Completed (Respondent) only)