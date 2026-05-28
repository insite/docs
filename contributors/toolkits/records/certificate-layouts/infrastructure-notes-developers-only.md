---
description: >-
  Developer setup for the Microsoft SSRS certificate-generation utility, plus
  proposed improvements to the certificate workflow
---

# Infrastructure notes - developers only

If you are working in your local environment then you need to pull the "Microsoft SSRS" repo from GitHub, and configure the web application in your local IIS.

The Microsoft SSRS web application is a lightweight utility that is responsible for generating certificate output files (PDF and PNG).

* Site Name = Microsoft SSRS
* Host Name = [local-ssrs.insite.com](http://local-ssrs.insite.com/)
* Port 443
* Physical Path = D:\Base\Repos\InSite\Microsoft.SSRS\Source

You can test with this URL:

* [https://local-ssrs.insite.com/certificates/certificatetest.aspx](https://local-ssrs.insite.com/certificates/certificatetest.aspx)

## Proposed Improvements

The following code and database changes are recommended to simplify the process for adding new certificates, and to decrease the need for developer intervention:

1. Rename the table from "achievements.TCredentialLayout" to "records.TCertificateLayout".
2. Implement web forms to search/create/edit/delete rows in the database table where certificate layouts are stored.
3. Eliminate the need for an administrator to remember the syntax for the Portal page URL where a user views and downloads the certificate associated with a v1 Course Activity.
   * admin/courses/resources/edit
   * Remove the Certificate tab from the Content panel
   * Add to the Settings tab (in the Course panel) a new field "Certificate Layout", with a drop-down list that allows you to select a Certificate Layout
   * Modify the v1 Course Outline page in the Portal so that when you click the Action button for a Certificate asset, it navigates to the page /ui/portal/records/credentials/certificate
