# Permissions (Proposed Improvement)

## Permission Overview <a href="#permissions-proposedimprovement-permissionoverview" id="permissions-proposedimprovement-permissionoverview"></a>

A permission has three attributes:

1. Role
2. Resource
3. Function

An example of a permission is this:

* **Platform Administrators** are permitted to **Edit** the **survey form ABC**.

In this example:

1. **Role** = Platform Administrators
2. **Resource** = survey form ABC
3. **Function** = Edit

We can represent all the permissions in the system (or any subset of permissions) in the form of a table with a column for each of these attributes. For example:

| **Role** | **Resource**                                            | **Function**           |
| -------- | ------------------------------------------------------- | ---------------------- |
| Alpha    | Assessment Attempt 6572e063-5dc0-401b-ad09-49ec04099c8c | Read                   |
| Alpha    | Assessment Attempt 6572e063-5dc0-401b-ad09-49ec04099c8c | Write                  |
| Alpha    | Assessment Attempt 6572e063-5dc0-401b-ad09-49ec04099c8c | Delete                 |
| Alpha    | ui/admin/home                                           | Execute                |
| Beta     | All Assessment Attempts                                 | Grade voice recordings |
| Beta     | ui/admin/contacts/people/search                         | Create                 |

## Roles <a href="#permissions-proposedimprovement-roles" id="permissions-proposedimprovement-roles"></a>

A role is a unique individual or group of individuals to whom permissions may be granted. Each role has these important properties:

* Identifier: This is a GUID that uniquely identifies the role.
* Category: Defines the type of role. Category values include Group, Person, and User.
* Name: A user-friendly and display-friendly name for the role. Ideally, this should be unique.
* Slug: This is a URL-friendly code that uniquely identifies the role.

### Role Types <a href="#permissions-proposedimprovement-roletypes" id="permissions-proposedimprovement-roletypes"></a>

A **Group** is a list of people in an organization. Permissions granted to a group are implicitly granted to every person in the group.

A **Person** is a specific individual user in a specific organization. Permissions granted to a person are applied only in the organization to which the person is assigned.

A **User** is an individual who may have access to multiple organizations. Permissions granted to a user are applied in all organizations to which the user is assigned.

## Resources <a href="#permissions-proposedimprovement-resources" id="permissions-proposedimprovement-resources"></a>

A resource is a unique object to which access may be granted. Each resource has these properties:

* Identifier: This is a GUID that uniquely identifies the resource.
* Category: Defines the type of resource. Category values include API Endpoint, UI Directory, UI Form, UI Element, Data Aggregate, Data Entity, and Data Field.
* Name: A user-friendly and display-friendly name for the role. Unique names are recommended but not required.
* Slug: This is a URL-friendly code that uniquely identifies the role.
* Location: This helps to locate the resource. Location values include API, User Interface, and Database.

### Resource Types <a href="#permissions-proposedimprovement-resourcetypes" id="permissions-proposedimprovement-resourcetypes"></a>

An **API Endpoint** is a specific URL to which API requests may be submitted.

A **Web Directory** is a listing of closely related web application forms (i.e. pages within the user interface). For example, all the URLs for administration of assessments are in the directory "ui/admin/assessments/home".\
A **Web Form** is a specific web application form with a specific URL. For example, the administration home page is "ui/admin/home".\
A **Web Element** is a specific part of a specific web form. For example, the Search Results tab on the search form for contact people is an element of that page.

A **Data Aggregate** is a type of database object where Timeline features have been implemented. This includes Achievement, Attempt, Bank, Credential, Event, Glossary, Group, Message, Page, Progress, Registration, Response, Site, and Survey.\
A **Data Entity** is a specific record in a specific database table. This can be used for row-level security rules.\
A **Data Field** is a specific field in a specific database table. This can be used for column-level security rules.

> A resource might be a single object to which a permission is granted, or it might be a collection of multiple objects. For example “All assessment attempts” or “Survey forms with names that start with the letter A”.

## Functions <a href="#permissions-proposedimprovement-functions" id="permissions-proposedimprovement-functions"></a>

A function is a unique type of operation that may be performed on a resource. Each function has these properties:

* Identifier: This is a GUID that uniquely identifies the function.
* Category: Defines the type of function. Category values include Access, Capability, and Command.
* Name: A user-friendly and display-friendly name for the function. This must be unique.
* Slug: This is a URL-friendly code that uniquely identifies the function.

### Function Types <a href="#permissions-proposedimprovement-functiontypes" id="permissions-proposedimprovement-functiontypes"></a>

An **Access** function is any one of the basic 7 general-purpose verbs used to identify a level of access: Execute, Read, Write, Create, Delete, Administrate, Configure.

A **Capability** function identifies a specific feature within the application. For example, the ability to grade voice recording questions in an assessment attempt. Currently, we have no comprehensive listing of all possible values for this function type, but we can work toward building a documented inventory of these.

A **Command** function identifies a specific Timeline command within the application. A role that is granted access to a command has permission to submit that command to the platform. For example, “Schedule Exam Event” is a command in the Events toolkit.

## Assumptions <a href="#permissions-proposedimprovement-assumptions" id="permissions-proposedimprovement-assumptions"></a>

1. It may (or may not) be feasible to pre-define the list of available functions for a given resource type and/or resource instance.
   1. To discover this, I think we need to build a representative table of system permissions and see what patterns emerge. This exercise can be done in an Excel workbook.
2. A resource that has at least one permission entry is understood to have security rules enabled.
   1. In this scenario, permission to perform any function on any resource is denied by default, and granted only when a permission exists to explicitly grant permission to perform that function on that resource.
   2. It may (or may not) be feasible to consider “Function” an optional attribute of a permission. If the Function is omitted from a permission entry, then (in theory) this could be defined to mean “All Functions”. The ambiguity here might decrease the administrative burden in managing permissions, but might increase confusion because such permissions would no longer be explicitly declared.
3. A resource that has no permission entries is understood to have security rules disabled.
   1. In this scenario, users should assume no permissions are applied or enforced by the system. If a resource must be inaccessible by default, then a user can create a role to represent this (e.g. a group named “Nobody” containing zero users), and then create a permission granting access to this role - and only this role.
