# Organization Specific Settings (Advanced Configuration)





* Assessments
  * LockPublishedQuestions (true/false)
  * DisableStrictQuestionCompetencySelection (true/false)
  * EnableQuestionSubCompetencySelection (true/false)
  * AttemptGradingAssessor (true/false)
  * RubricReGradeKeepInitialScores (true/false)
  * ShowPersonNameToGradingAssessor (true/false)
* Contacts
  * OrganizationIndustry (Industry Specialist)
  * Full Name Policy
  * AutomaticGroupJoin
  * PersonCodeAutoincrement (true/false)
  * PersonCode Text Translation
* Events
  * ShowUnapplicableSeats (true/false)
  * DisableClassExams (true/false)
  * AllowUsersRegisterEmployees (true/false)
  * AllowUserAccountCreationDuringRegistration (true/false)
  * CompanySelectionAndCreationDisabledDuringRegistration (true/false)
  * AllowClassRegistrationFields (true/false)
  * Class Registration Account Panel
* Portals
  * ShowMyDashboard (true/false)
* Surveys
* Integrations
  * Prometric
  * SCORM
* Sign-In Page
* NCSHA

### Assessments <a href="#organizationspecificsettings-advancedconfiguration-assessments" id="organizationspecificsettings-advancedconfiguration-assessments"></a>

[**Organization Specific Settings**](https://e02.insite.com/ui/admin/accounts/organizations/search)



#### LockPublishedQuestions (true/false) <a href="#organizationspecificsettings-advancedconfiguration-lockpublishedquestions-true-false" id="organizationspecificsettings-advancedconfiguration-lockpublishedquestions-true-false"></a>

If this setting is set to "true" and Admin is not able to edit a question that has been published. The edit icon () will not be visisble. If setting is set to "false" then the edit icon () will be visible.

* **Page URL:** /ui/admin/assessments/banks/outline
* **Page URL:** /ui/admin/assessments/forms/workshop

```
"LockPublishedQuestions": false,
```

#### DisableStrictQuestionCompetencySelection (true/false) <a href="#organizationspecificsettings-advancedconfiguration-disablestrictquestioncompetencyselection-true-fal" id="organizationspecificsettings-advancedconfiguration-disablestrictquestioncompetencyselection-true-fal"></a>

This setting allows Administrators to attach Competencies to a question that is in any area that is available in the Framework that is attached to the Assessment Bank.

* **Page URL:** /ui/admin/assessments/questions/change

```
"DisableStrictQuestionCompetencySelection": true,
```

#### &#x20;EnableQuestionSubCompetencySelection (true/false) <a href="#organizationspecificsettings-advancedconfiguration-enablequestionsubcompetencyselection-true-false" id="organizationspecificsettings-advancedconfiguration-enablequestionsubcompetencyselection-true-false"></a>

* **Page URL:** /ui/admin/assessments/questions/change

```
"EnableQuestionSubCompetencySelection": true,
```

#### AttemptGradingAssessor (true/false) <a href="#organizationspecificsettings-advancedconfiguration-attemptgradingassessor-true-false" id="organizationspecificsettings-advancedconfiguration-attemptgradingassessor-true-false"></a>

This setting allows Administrators to assign a Grading Assessor to an Assessment Attempts in a “Pending” status so that Composed Response questions can be graded.

If **AttemptGradingAssessor** is set to “**true**”, then a Group = Role for the Grading Assessors need to be created with the [Grade](https://sandbox-inspire.insite.com/ui/admin/platform/routes/edit?id=98034666-463a-443d-91ff-f395e75493b4\&return=M1KfYwACEaNjShx8LYFMpjuxAAFCiBgJBQA1) and [Design/Grading Assessors](https://sandbox-inspire.insite.com/ui/admin/platform/routes/edit?id=3fd0d220-e8e3-40a8-846f-95cd4f7eb6a3\&return=M1KfYwACEaNjShx8LYFMpjuxAAFCiBgJBQA1) permissions.

* **Page URL:** /ui/admin/assessments/attempts/reports/search

```
"AttemptGradingAssessor": true,
```

#### RubricReGradeKeepInitialScores (true/false) <a href="#organizationspecificsettings-advancedconfiguration-rubricregradekeepinitialscores-true-false" id="organizationspecificsettings-advancedconfiguration-rubricregradekeepinitialscores-true-false"></a>

When the Setting is Set to "True", any points assigned to a rubric during the initial grading of a question will remain selected when the attempt is regraded. The grading assessor has the option to update the score during the regrade process or leave the score unchanged.

If a rubric, that was previously attached to a question in an attempt, is updated and the question is rescored, the score for that question will not be automatically populated. This is because the rubric changes could potentially impact the scoring criteria, requiring the assessor to manually reassess the question based on the updated rubric.

When the Setting is Set to "False", all rubric scores are cleared when an attempt is regraded, meaning no points assigned to the rubric during the initial grading will be retained. Every question needs to be regraded from scratch, as all prior scoring is removed.

* **Page URL:** /ui/admin/assessments/attempts/grade

```
"RubricReGradeKeepInitialScores": false,
```

#### **ShowPersonNameToGradingAssessor (true/false)** <a href="#organizationspecificsettings-advancedconfiguration-showpersonnametogradingassessor-true-false" id="organizationspecificsettings-advancedconfiguration-showpersonnametogradingassessor-true-false"></a>

If **AttemptGradingAssessor = true** during the grading process an Grading Assessor can either see the users Full Name and Person Code or only the Person Code.

When the setting is set to “true”, then Full Name and Person Code will be visible to the Grading Assessor. When the setting is set to “false”, then only Person Code is visible to the Grading Assessor.

**Page URL:** /ui/admin/assessments/assessor/view

**Page URL:** /ui/admin/assessments/assessor/grade

```
"ShowPersonNameToGradingAssessor": false
```

### Contacts <a href="#organizationspecificsettings-advancedconfiguration-contacts" id="organizationspecificsettings-advancedconfiguration-contacts"></a>

[**Organization Specific Settings**](https://global.insite.com/ui/admin/accounts/organizations/search)



#### OrganizationIndustry (Industry Specialist) <a href="#organizationspecificsettings-advancedconfiguration-organizationindustry-industryspecialist" id="organizationspecificsettings-advancedconfiguration-organizationindustry-industryspecialist"></a>

* **Page URL:** /ui/admin/contacts/people/edit
* Display Custom Fields card in users contact record



* Display Jobs Access checkbox



#### Full Name Policy <a href="#organizationspecificsettings-advancedconfiguration-fullnamepolicy" id="organizationspecificsettings-advancedconfiguration-fullnamepolicy"></a>



The Full Name Policy allows Organizations to specify the pattern to be used for Full Names in Shift iQ

* {First} {Last}
* {First} {Middle} {Last}
* {Last}, {First}
* {Last}, {First} {Middle}

**Example:**

```
"FullNamePolicy": "{First} {Middle} {Last}"
```

#### AutomaticGroupJoin <a href="#organizationspecificsettings-advancedconfiguration-automaticgroupjoin" id="organizationspecificsettings-advancedconfiguration-automaticgroupjoin"></a>

* **Page URL:** /ui/portal/contacts/people/create

When **AutomaticGroupJoin** is set with a **Group Unique Identifier**, every contact added through the /ui/portal/contacts/people/create page will automatically be added to that group.

**Example:**

```
"AutomaticGroupJoin": "0c57b958-d894-4ff1-be42-b0050009fc1f"
```

#### PersonCodeAutoincrement (true/false) <a href="#organizationspecificsettings-advancedconfiguration-personcodeautoincrement-true-false" id="organizationspecificsettings-advancedconfiguration-personcodeautoincrement-true-false"></a>

* **Page URL:** /ui/admin/contacts/people/edit

When **PersonCodeAutoincrement** settings is set to "**true**", then each new contact record that is being created will automatically be assigned a system generated Person Code (Learner ID).

#### PersonCode Text Translation <a href="#organizationspecificsettings-advancedconfiguration-personcodetexttranslation" id="organizationspecificsettings-advancedconfiguration-personcodetexttranslation"></a>

If the org wants to have their own terminology used instead of “Person Code”, you can add an English Translation in Labels (/ui/admin/assets/labels/edit?label=Person+Code) to their desired wording, and it will update it throughout the UI.

### Events <a href="#organizationspecificsettings-advancedconfiguration-events" id="organizationspecificsettings-advancedconfiguration-events"></a>

[**Organization Specific Settings**](https://global.insite.com/ui/admin/accounts/organizations/search)



#### ShowUnapplicableSeats (true/false) <a href="#organizationspecificsettings-advancedconfiguration-showunapplicableseats-true-false" id="organizationspecificsettings-advancedconfiguration-showunapplicableseats-true-false"></a>

Display all seats or only seats applicable to user during Class Registration.

* **Page URL:** /ui/portal/events/classes/register



#### DisableClassExams (true/false) <a href="#organizationspecificsettings-advancedconfiguration-disableclassexams-true-false" id="organizationspecificsettings-advancedconfiguration-disableclassexams-true-false"></a>

Dsiplay/Hide Assessment Form column and Exam Password

* **Page URL:** /ui/admin/events/classes/outline



#### AllowUsersRegisterEmployees (true/false) <a href="#organizationspecificsettings-advancedconfiguration-allowusersregisteremployees-true-false" id="organizationspecificsettings-advancedconfiguration-allowusersregisteremployees-true-false"></a>

Display/Hide the Register Employees button

* **Page URL:** ui/protal/classes/outline



#### AllowUserAccountCreationDuringRegistration (true/false) <a href="#organizationspecificsettings-advancedconfiguration-allowuseraccountcreationduringregistration-true-f" id="organizationspecificsettings-advancedconfiguration-allowuseraccountcreationduringregistration-true-f"></a>

Display/Hide the Register New Employee link during class registration.

* **Page URL:** /ui/portal/events/classes/register-employee



#### CompanySelectionAndCreationDisabledDuringRegistration (true/false) <a href="#organizationspecificsettings-advancedconfiguration-companyselectionandcreationdisabledduringregistra" id="organizationspecificsettings-advancedconfiguration-companyselectionandcreationdisabledduringregistra"></a>

Allow or Disallow the selection and creation of Employers during class registration.

* **Page URL:** /ui/portal/events/classes/register



#### AllowClassRegistrationFields (true/false) <a href="#organizationspecificsettings-advancedconfiguration-allowclassregistrationfields-true-false" id="organizationspecificsettings-advancedconfiguration-allowclassregistrationfields-true-false"></a>

Turn on/off the Class Settings tab, so that administrators can set what fields should be visible/hidden and editable/non-editable during class registration. Each class can be customized.

* **Page URL:** /ui/admin/events/classes/outline



#### Class Registration Account Panel <a href="#organizationspecificsettings-advancedconfiguration-classregistrationaccountpanel" id="organizationspecificsettings-advancedconfiguration-classregistrationaccountpanel"></a>

We are able to add/remove fields under the Accounts panel on the Class Registration page.

To add/remove fields, open the Organization settings and select the different fields under the Fileds and Class Registration tab.



### Portals <a href="#organizationspecificsettings-advancedconfiguration-portals" id="organizationspecificsettings-advancedconfiguration-portals"></a>

[**Organization Specific Settings**](https://global.insite.com/ui/admin/accounts/organizations/search)



#### ShowMyDashboard (true/false) <a href="#organizationspecificsettings-advancedconfiguration-showmydashboard-true-false" id="organizationspecificsettings-advancedconfiguration-showmydashboard-true-false"></a>

* **Page URL:** /ui/portal/reports/dashboard/account-settings



### Surveys <a href="#organizationspecificsettings-advancedconfiguration-surveys" id="organizationspecificsettings-advancedconfiguration-surveys"></a>

[**Organization Specific Settings**](https://global.insite.com/ui/admin/accounts/organizations/search)



* **EnableUserConfidentiality (true/false)**
  * **Page URL:** /ui/admin/surveys/forms/outline
* **LockUserConfidentiality (true/false)**
  * **Page URL:** /ui/admin/surveys/forms/outline



### Integrations <a href="#organizationspecificsettings-advancedconfiguration-integrations" id="organizationspecificsettings-advancedconfiguration-integrations"></a>

[**Organization Specific Settings**](https://global.insite.com/ui/admin/accounts/organizations/search)

#### Prometric <a href="#organizationspecificsettings-advancedconfiguration-prometric" id="organizationspecificsettings-advancedconfiguration-prometric"></a>

Sends Eligibility status of class registrants to Prometric.

```
"Prometric": {
      "ClientCode": "ProgramID",
      "UserName": "UserName",
      "Password": "Password"
    },
```



The ProgramID, UserName and Password needs to be provided to Shift iQ by Prometric or the Organization using Prometric.

#### SCORM <a href="#organizationspecificsettings-advancedconfiguration-scorm" id="organizationspecificsettings-advancedconfiguration-scorm"></a>

SCORM Cloud login credentials (**AppId** and **Secret Key**) can be found here: [https://app.cloud.scorm.com/sc/user/Apps](https://app.cloud.scorm.com/sc/user/Apps)

```
"ScormCloud": {
      "UserName": "",
      "Password": ""
    }
```



### Sign-In Page <a href="#organizationspecificsettings-advancedconfiguration-sign-inpage" id="organizationspecificsettings-advancedconfiguration-sign-inpage"></a>

After the 25.1 release (February 19, 2025), the Google and Microsoft Sign-In buttons will be customizable per organization.

**URL: /ui/lobby/signin**



```
"SignIn": {
      "AllowGoogleSignIn": false,
      "AllowMicrosoftSignIn": false
    }
```



### NCSHA <a href="#organizationspecificsettings-advancedconfiguration-ncsha" id="organizationspecificsettings-advancedconfiguration-ncsha"></a>

In the fall, NCSHA will request that this setting is turned to true so their users can see the newly published reports. Shortly after Jan 1 of each year, change this setting back to FALSE so users can’t see the newly previous year. Also add the new year as a period early in the new year.



```
"NCSHA": {
  "ShowLastYearToEveryone": false
  },
```
