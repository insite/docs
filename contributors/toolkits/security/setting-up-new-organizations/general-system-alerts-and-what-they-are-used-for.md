---
description: >-
  Reference for the general system alerts sent by the platform, who receives
  them, their purpose, and the variables each one supports
---

# General system alerts and what they are used for

## System Alerts that go to all Users

These Alerts are sent by the system to all users, regardless if they are added to a specific customer's Message Alerts or not. In the case of the UserAccountWelcomed alert, it's a good idea to add this to each new Org so they can customize it to their branding and workflows.

**Note:** Once any of our Message templates has been added to a customer's account as an alert, it can no longer be duplicated or used as a notification.

| **Alert Information** | **Purpose and Notes** | **Variables that work with it** |
| --- | --- | --- |
| **UserAccountWelcomed**<br>Default Subject: User Account Approved - Welcome!<br>Goes to: Users | This notification is sent to a user when an admin grants them access to the platform. It can also be sent manually to the user at any time. (It isn't sent to users who are granted access when they create their own accounts.) | FirstName, Email, CompanyTitle, SignInUrl, PasswordInstruction, PasswordInstruction:en, PasswordInstruction:fr, Password |
| **UserAccountCreated**<br>Default Subject: User Account Registered<br>Goes to: User | This notification is sent to any user who self-registers for a new account, confirming receipt of the registration information. | Name, Email, Phone, City, Province, CompanyTitle |
| **UserRegistrationSubmitted**<br>Default Subject: Account Created<br>Goes to: Subscribers | This notification is sent to admin subscribers after a new user account is created by another administrator. | ApprovalUrl, City, Email, FirstName, LastName, Name, Organization, Phone, Province, RegistrationUrl, Thumbprint |
| **UserOTPActivationCode**<br>Default Subject: Your verification code from InSite<br>Goes to: User | This alert is sent to any user who has multi-factor authentication enabled and is logging in, and it includes a one-time use code. | ConfirmationCode, Organization |
| **UserEmailVerificationRequested**<br>Default Subject: Email Verification Requested<br>Goes to: User | This notification is sent to every user that self registers for their own account that is automatically granted access. | AppUrl, Organization, UserEmail, UserIdentifier, VerifyEmailUrl |
| **PasswordResetRequested**<br>Default Subject: Password Reset Requested<br>Goes to: User | This alert is sent to any user that requests a password reset. | ResetUrl |
| **PasswordChanged**<br>Default Subject: Password Changed<br>Goes to: User | This alert is sent to any user that changes their password. | UserEmail, EventTime, BrowserAddress |
| **ApplicationAccessGranted**<br>Default Subject: Application Access Granted<br>Goes to: User | This notification is sent to a user when access is granted to the platform after being requested. | ApproverEmail, ApproverName, Organization, UserAccess, UserFirstName |
| **UserEmailSubscriptionModified**<br>Default Subject: Mailing List Subscriptions Modified<br>Goes to: User | This notification is sent to any user who modifies their own mailing list group memberships. (Configured in each List group.) | RecipientName, RecipientMemberships |
| **UnsubscribeSuccess**<br>Default Subject: Successfully Unsubscribed<br>Goes to: User | This notification is sent to any user who unsubscribes themselves from all marketing emails from an organization. | UserEmail, Organization, ResubscribeUrl |

## System Alerts that go to Admin Subscribers

These alerts should be added to every new customer, with at least one of their admins as a subscriber. Also suggest updating the subject or contents to include text indicating it's coming from Shift iQ and why.

| **Alert Information** | **Purpose and Notes** | **Variables that work with it** |
| --- | --- | --- |
| **HelpRequested**<br>Default Subject: Workflow Assignment - Help Requested<br>Goes to: Admin Subscribers | This notification is sent to admin subscribers when a portal user completes the Shift iQ Support request form. (update Subject to: A Shift iQ user is requesting support) | BrowserAddress, BrowserName, Organization, RequestDescription, RequestSummary, RequestUrl, UserEmail, UserEmployer, UserName, UserPhone |
| **AuthenticationAlarmTriggered**<br>Default Subject: Authentication Failed (Brute-Force Login Attempt)<br>Goes to: Admin Subscribers | This alert is sent to admin subscribers when a user fails multiple attempts to sign in to the platform. | FailedLoginCount, Organization, SignInUrl, UserEmail, UserHostAddress |
| **ApplicationAccessRequested**<br>Default Subject: Application Access Requested<br>Goes to: Admin Subscribers | This notification is sent to admin subscribers when a user requests access to the platform in the lobby. (If access has been removed from an existing user, they can ask for it back with this.) | AppUrl, Organization, SourceUrl, UserEmail, UserIdentifier, UserName<br>ApproveAccessUrl also works here, but isn't listed; this takes admins to the ui/admin/contacts/people/approve-access screen |

## Other Available Alerts not currently being used by any customers

| **Alert Information** | **Purpose and Notes** | **Variables that work with it** |
| --- | --- | --- |
| **PersonCommentFlagged**<br>Goes to: Admin Subscribers | This notification is sent to admin subscribers when a flag is added to any comment on any contact record. | AuthorFirstName, AuthorLastName, AuthorEmail, TopicFirstName, TopicLastName, TopicEmail, CommentText |
| **EmployerGroupCreated**<br>Goes to: Admin Subscribers | This notification is sent to admin subscribers when an Employer group is created. | GroupName |
| **EventVenueChanged**<br>Goes to: Admin Subscribers | This notification is sent to admin subscribers when a group is selected or changed as the venue for an event. | GroupIdentifier, GroupName, EventIdentifier, EventDate, EventName, EventNumber |
| **CredentialCreated**<br>Sent to: Users, if added to an org (ADD WITH CAUTION, once added, it can't be turned off and will send for every achievement) | This notification is sent to any user that is assigned or granted an achievement. | AchievementName, AchievementType, LearnerEmail, LearnerFirstName, LearnerIdentifier, LearnerLastName |
| **UserAccountCreated**<br>Goes to: Admin Subscribers | This notification is sent to admin subscribers after a new user account is created by another administrator. | Name, Email, Phone, City, Province, CompanyTitle |
| **IssueOwnerChanged**<br>Goes to: Admin Subscribers | This notification is sent to admin subscribers when a case owner is assigned or changed on any case. | IssueNumber, IssueType, IssueStatus, IssueSummary, OwnerFirstName, OwnerLastName, OwnerEmail |
