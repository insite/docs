# Setting Up New Organizations

### New Account Setup in Jira <a href="#settingupneworganizations-newaccountsetupinjira" id="settingupneworganizations-newaccountsetupinjira"></a>

* steps to create a project
* list of initial tasks to create in the project: XXXX Account Management (Ongoing), Initial Configuration, Administrator Training
* steps to create a Tempo account
* steps to create the customer in Support and invite their admins

### New Account Setup in Microsoft Teams <a href="#settingupneworganizations-newaccountsetupinmicrosoftteams" id="settingupneworganizations-newaccountsetupinmicrosoftteams"></a>

* steps to copy the Customer Team
* steps to invite admins to the team for sharing files/chats, etc.
* steps to sync the new team’s folder to your OneDrive

### New Account Setup in Shift iQ <a href="#settingupneworganizations-newaccountsetupinshiftiq" id="settingupneworganizations-newaccountsetupinshiftiq"></a>

* Decide if the new customer will be created in an existing partition or a new one (if the latter, see creating a new partition)
* Create the account in /ui/admin/accounts/organizations/create of the desired/new partition:
*
  * Parent organization - Global (except for Keyera orgs, use CMDS) **Note:** this is what gives us Platform Admins all the permissions we need to be boss.
  * Organization Code - this is what their portion of the url will be with .insite.com or .shiftiq.com
  * Organization Name - this is what is seen as their name inside Shift iQ, both by us and our customers, as well as in any alerts with the placeholder of $OrganizationName
  * Full Legal Name - can be same as Organization Name, but if using an acronym, suggest full name here for reference
  * Organization Domain
  * Organization Web Site URL - leave blank
  * Remaining fields are optional, can be left blank
* In the newly created account, **Configuration** tab
*
  * **Platform** subtab, user registration card - this is where you configure the desired New User Journey:
  *
    * Do not allow new users to self register - select if account wants to manually add all new users themselves, no self registration allowed (i.e., Insite, BCPVPA)
    * Allow anyone to self register on user login screen - select if account wants any user to self register, either all to a specified role group, or be able to see a list of role groups where self-subscribe is enabled\
      Note: when this is selected, the New Users tab appears on the login screen
    * Allow new users to self-register by link only - select if account wants to use specific links to each role group that allows self-subscribe, the New Users tab isn’t visible so users can only register using the links
    * Automatically grant Portal (learner) access to self-registered users - select if account doesn’t want to review self-registered new user accounts before they have access to a portal (if selected, ensure account is configured to give something to new users, not just a blank portal; if unselected, ensure account has the **AccessRequested** alert configured)
    * Settings card can be ignored
  *
  * **Advanced** subtab, see [Advanced configuration](../../../../../components/utility-components/security/setting-up-new-organizations/broken-reference/) topic
* Configuration for desired New User Journey
*
  * Do they want the New Users tab visible or not
  * Do they want New Users to self-register: if yes, must have a Role group with “allow users to subscribe themselves” checked off
  * Do they want New Users to be immediately granted access, or be reviewed first
* Contact and Group Configuration (Add admin groups, give permissions, add admins, also add admins to Insite org and the Subscribe to SpotLite list so they get our Newsletter)
* Create senders for org
* Add all alerts org requires (at least **UserRegistrationSubmitted, HelpRequested & AccessRequested**) and ensure the latter two are going to someone
* Add portal Logo, light and dark
* Add login logo
* Bambora
* SCORM
* Add any global admins that will need access to the new org, including yourself, not including any devs
* Create a Portal if required
* Create custom collections (e.g. Gender fields) if requested
