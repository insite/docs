---
description: >-
  Admin toolkit permissions to grant to admin and design roles, including
  permissions to grant with caution and route-level permissions
---

# Granting admin permissions to roles

These Permissions are needed for general Admin toolkit access if the customer is using that toolkit:

* Toolkits (must add for all admin and design roles)
* Admin/Assessments
* Admin/Assessments/Attempts (only if admins should see attempts)
* Admin/Assessment/Quizzes (for typing speed and data entry quiz access)
* Admin/Contacts
* Admin/Courses
* Admin/Events
* Admin/Events/Classes (must add if giving access to Events)
* Admin/Invoices (sales toolkit, all but Payments tile)
* Admin/Jobs
* Admin/Messages
* Admin/Payments (visibility of Payments tile in sales toolkit)
* Admin/Records
* Admin/Records/Achievements (must add to allow admins to work with Achievements)
* Admin/Reports
* Admin/Sites
* Admin/Standards
* Admin/Surveys
* Admin/Surveys/Responses (must add to allow admins to see respondent names for non-confidential responses, except for COTBC and CPTBC)
* Admin/Workflow
* Impersonate (only if admins should be able to impersonate other users)

These Permissions should be granted with caution, and only when needed (most are already available to Operators, so don't need to be added even to Platform Admin groups):

* Admin/Assets - for glossary and labels access
* Admin/Assets/Uploads - for uploads card access
* Admin/Assets/Contents – for Contents tile visibility, not sure what this really does
* Admin/Surveys/Responses/Change (only if admins should be allowed to edit survey responses, currently only NCSHA doing this)
* Admin/Events/Exams – only for STBC use
* Admin/Accounts – operators can access Accounts on Utilities dropdown
* Admin/Settings – operators can access Setup on Utilities dropdown
* Admin/Integrations – operators can access Integrations on Utilities dropdown, if an org needs access, use a custom tile to get admins to ui/admin/integrations/api-requests/search and then give them permissions on the two forms as per below.
* Admin/Testers - controls visibility of 2 additional tiles on Integrations card, mostly for STBC support
* Admin/Polaris – only for Insite website editors, being moved elsewhere so will be obsolete

In addition, there are these, where permission can be given directly to a role by editing the route itself from /ui/admin/platform/routes/search (it can't be granted using the Grant Permission button in the Group):

* admin/records/gradebooks/outline/create-scores – visibility of Create Scores button in gradebook
* ui/admin/assessments/attempts/grade - not sure what this controls but Inspire graders have been added to this in e06
* admin/assessments/attempts/grade/regrade – visibility of the Regrade button on attempts with manually graded questions
* ui/admin/contacts/people/edit/socialinsurancenumber – shows SIN field unmasked
* ui/admin/contacts/people/upload/update – allows admins to update existing contacts using the upload contacts form; without it they can only add new contacts (grant with caution, one customer used this to change a bunch of their contacts to first name = F and last name = L)
* ui/admin/integrations/api-requests/search and ui/admin/integrations/api-requests/outline – for admins that need to search and view their API calls, create custom admin tile as well
* ui/admin/messages/emails/search – visibility of Emails tile on Messages home screen
