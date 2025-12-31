# Editing Contacts

This screen contains all of the information related to each contact in Shift iQ. Find and update personal details, employment info, addresses, any related uploaded documents, internal comments, a history of changes to the contact record, and more on the **Persons** tab. Use the **Memberships** tab to see and edit the groups they belong to and other relationships. The **Records** tab contains links to a variety of assets the contact may have generated. Grant and control access on the **System Access** tab.

**Deleting a Contact Record:** Deleting contact records should be used with **caution**. Deleting a contact will remove the link to all of their activitity in the system and is typically only done with duplicate records that have never logged in. If it is someone who has had activity but left your organization, it is better to Archive the user and remove their access to the system using the Sign In tab.

**Edit:** Make changes to any of the fields in the Person panel and click **Save**.

**New:** You can ‘create another contact’ using the ‘New’ button

**View Change History:** To view the change history of a specific user or contact

**Report:** To get record of contacts detailed data

(Note that some of the options below are only available to admins with Write and Delete access.)<br>

#### Phone Number Auto-Configuration parameters

When an telephone number is added to a users Contact Record, Shift iQ automatically configurates the phone number based on the number of digits added:

* If you save the record with **10 digits** in any of the phone fields, our system adds brackets around the first 3 digits, adds a space after the second bracket and adds a dash before the last four digits. **Example:** 1234567890 ![phone-number-1.png](https://e02.insite.com/files/web/a53ae6fb-9834-4fd4-960b-b09300e40d6f/phone-number-1.png)
* If you put **11 digits** and save, it removes whatever the first digit is, adds brackets around the first 3 digits, adds a space after the second bracket and adds a dash before the last four digits. **Example:** 12345678901 ![phone-number-2.png](https://e02.insite.com/files/web/a53ae6fb-9834-4fd4-960b-b09300e40d6f/phone-number-2.png)
* If you put **periods** or **dashes** in between **10 or 11 digits**, our system removes those dots or dashes, adds brackets around the first 3 digits, adds a space after the second bracket and adds a dash before the last four digits. **Example:** 123-456-7890 / 1234-567-8901 ![phone-number-1.png](https://e02.insite.com/files/web/a53ae6fb-9834-4fd4-960b-b09300e40d6f/phone-number-1.png) ![phone-number-2.png](https://e02.insite.com/files/web/a53ae6fb-9834-4fd4-960b-b09300e40d6f/phone-number-2.png)
* BUT if you put **more** than **11 digits** in any of the number fields, our system converts it to a straight number, no characters. **Example:** 1234567890123 ![phone-number-3.png](https://e02.insite.com/files/web/a53ae6fb-9834-4fd4-960b-b09300e40d6f/phone-number-3.png)
