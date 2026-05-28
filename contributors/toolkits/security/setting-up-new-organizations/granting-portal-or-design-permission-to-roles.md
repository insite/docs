---
description: >-
  Portal and Design permissions to grant to roles, including which groups each
  permission should be given to
---

# Granting portal or design permission to roles

## Portal Permissions

Note: Although "Portal" is a permission, it does not need to be granted to any role, as all users already have Portal access by default. The other Portal permissions do need to be granted to both Portal and Admin groups that want to access the specific functionality from the Portal side. (In other words, these prevent a portal user without permission from accessing the related action paths even if they have obtained the direct URL.)

* Portal - not needed, all users already have access to subactions controlled by this permission
* Portal/Appointments - for any customer using Appointments in Events, allows portal users to search appointments off the Calendar, give to admin and portal calendar groups
* Portal/Classes - for any customer using Classes in Events, give to admin and registrant groups
* Portal/Contacts - for any customer using the portal contacts search screen; currently only Inspire and CAMLPR regulators
* Portal/Jobs - for any customer using Jobs, give to admin, candidate and employer groups
  * Portal/Jobs/Candidates - give to admin and candidate groups
  * Portal/Jobs/Employers - give to admin and employer groups
* Portal/Logbooks - give to admin, leaner and validator groups

## Design Permissions

These are meant to be restricted versions of our existing toolkits, for specific roles like Logbook validators, Attempt assessors, Gradebook instructors, and (soon) Content authors. Roles with these permissions see a custom view of the Admin home page, and can't navigate to other admin views.

* Design/Attempts - not sure what this was intended for
* Design/Gradebooks - for Instructors to view their students in a class, and view/update their grades\
  Design/GradingAssessors - for assessment questions that require manual grading
* Design/Progressions - not sure what this was intended for
* Design/Users - not sure what this was intended for
* Design/Validators - for Logbook validators to review and validate logbook entries
