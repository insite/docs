# Permissions

#### ClaimType.Action Permissions <a href="#permissions-claimtype.actionpermissions" id="permissions-claimtype.actionpermissions"></a>

If we want to check if given Identity User have permission for specific TAction or based on this we want to display a certain Accordion Panel or any other WebControl (either Display or Enable) we can follow those steps.

Add desired TAction row for example:

`"ui/portal/profile/employer-write"`

> Note that TAction permission should end with either READ, WRITE etc.

Create Group: `contacts.Group entry` table

> Best by SQL script

Add accounts to this Group, and insert ActionIdentifire with GroupIdentifire in: `contacts.TGroupAction` table

After that you can simply check like this:

`Identity.IsGranted(ClaimType.Action, "ui/portal/profile/employer-write");` to see if current logged in account has permissions or not.

For full example go to: [DEV-3454](https://insite.atlassian.net/browse/DEV-3454)
