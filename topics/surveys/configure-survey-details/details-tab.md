# Details Tab

#### IDENTIFICATION

**Internal Name (Required)**
The internal name is used as a reference for filing purposes. It is required, but it is not visible to the survey respondent.

**External Name**
This is the survey title displayed to the survey respondent and in survey invitations.

**Test Link**
Link for testing and viewing the survey. This URL is intended for use by Administrators only, to review and test the survey. It should NOT be shared with actual survey respondents.

**Lock Status**
Lock your survey if you want to prevent changes to the survey settings or questions.

**Hook/Integration Code**
Unique code for integration with internal toolkits and external systems.  The survey Hook is for integrating the survey with the Gradebook module.  If used, the identifier here must match the hook in the corresponding Gradebook.  

**Department**
The departments to which this survey is assigned.

#### CONFIGURATION

**Publication Status**
* **Draft:** A Drafted survey is open to responses from administrators only. 
* **Open (Published):** An Opened survey is open to all respondents.
* **Closed:** Responses are not accepted for a closed survey 
* **Archived:** Archived surveys no longer show up in the default search results. View archived surveys by explicitly searching for them using the Closed (Archived) search criteria.

**Opened Date**
The date and time when responses to the survey are opened to all respondents.

**Close Date**
New responses are not permitted after the survey is closed.

**Expected Duration (in Minutes)**
The number of minutes that a user is expected to need to complete this survey. If your survey is published to the Portal, the expected duration will show up on the survey card in portal. 

**Feedback for Respondents**
Allow respondents to review feedback from the survey administrator about answers they submitted to questions on the form. This is available for Radio Button style questions and is configured in the Question Options panel.
* **Summary Feedback:**  Summary Feedback will display all the question in the Survey a user answered, that has feedback enabled in the question itself. If questions were answered, but there is no feedback in that question, it will not show when Summary Feedback is selected. It will also display likert type questions, if likert style question were setup in your survey questions.
* **Detailed Feedback:**  Detailed Feedback will show the user all the question question in the survey, including the questions the user did not answer (or were not required to answer). 
* **Feedback Disabled:**  No feedback will be given to the user once the survey is completed.

**Limit Responses per Respondent**
Select Limited to ensure each respondent answers the survey only once (preferred). If you need to be able to download the name of responses, you must limit responses to one per person.  
* **Limited:** Allows respondents to answer the survey only once, but also allows identification of respondent. The Start Survey button goes away once a respondent has taken the survey once.  To allow them to take it again, you must either
	* Turn off the Limit response option
	* Delete the respondent’s answers
* **Unlimited:** Allows respondents to answer the survey an unlimited amount of times, and also allow anonymous responses.

**Allow Anonymous Responses**
Allow users to answer the survey without identifying themselves and without signing in.
