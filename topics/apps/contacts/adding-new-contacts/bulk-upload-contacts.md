Any organization's admins can upload **NEW** contacts with the bulk upload tool. However, this tool can also be used by those with permission to **bulk update** existing contacts. Typically, bulk updating should be done by Platform Administrators, or well-trained super admins, to prevent overwriting information that should be kept. Here's how our Support team can give the latter access:

1. Create a separate role group such as "Access to Contacts Upload" and just add the admins who should have access and know how to use it properly.
1. While logged in to the tenant account, click on **Settings**, then **Actions**. Set filter for action url of **admin/contacts/people/upload/update** and open that action.
1. In the **Authorization** panel, add the group that should have permissions to bulk upload, and save.
1. Admins will need to log out and back in before permissions will be applied to their accounts.