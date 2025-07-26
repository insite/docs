We've implemented the ability to move Assessment Banks from one Organization to another, and ratain the original Competency mapping.

**Download the question bank**
1. In the exporting organization, download the question bank by clicking on the **Download JSON** button in the **Assessment Bank**.

**Download the framework and the file with hooks in it**
1. Go to the Standards search screen in the organization from which you are exporting the framework.
2. Change your search results to search for all Standard Types, by selecting the blank option from the dropdown list.
3. Under the **Settings** heading, change the column visibility so that you can only see the Hook and Title columns.
4. Click the Search button. You will get more than you need, but it does not matter because the hooks will be unique.
5. Click on the Download tab and download all the search results.
6. In the *.csv / *.xlsx download, change the order of the columns so that **Standard Identifier** is in **Column A** and **Standard Hook** is in **Column B**.
7. Delete the 1st row in the spreadsheet and save your changes.
8. Now you can proceed to download the Competency Framework you want.

**Upload the framework**
*DON’T UPLOAD YOUR FRAMEWORK TO THE ORIGINAL ORGANIZATION ACCOUNT.*
1.  In the new organization, open the **Standards** toolkit and then click on **Add New Standard** at the top of the page.
2. Select **Upload one new standard from a file** from the dropdown list.
3. Select the *.json file for the Competency Framework you downloaded and upload it normally. The hooks will automatically be uploaded. 

**Upload the bank**
1.  In the new organization, open the **Assessment** toolkit and then the **Banks** tile. 
2.  Click on the **Add New Bank** link at the top of the page and select **Upload one new bank from a file** link from the dropdown list.
2. Select the *.json file for the **Assessment Bank** you downloaded.
3. In the **Standard Hooks** box, paste the first 2 columns (Standard Identifier, Standard Hook) of the spreadsheet that maps the hooks with the standards identifiers
4. Click the **Save**.