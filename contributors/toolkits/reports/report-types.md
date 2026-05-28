---
description: The types of reports available in the platform and their relative cost
---

# Report types

**Last Search**. The system automatically stores the criteria for your "last search" on every search page. You can select your own Criteria to Filter the Results, select your own Columns for the Results (and the Download spreadsheet), and your "last search" is always loaded by the system whenever you revisit a search page. These reports are universal and free to customers.

**Saved Search**. You can save your Criteria Filter and Column Download settings on every Admin Search page. These reports are also universal and free to customers.

**Ad Hoc Report**. This is a report built by an administrator using the Ad Hoc Report Builder form. Input from a developer is needed only to add a requested table to the list of available tables for ad hoc reporting. This is done one time only, and is then available to all customers, making these reports free to all customers (immediately following the initial one-time setup).

**Ad Hoc Query**. This is a SQL query copied and pasted into a query page that is accessible to InSite Admins only. The size and complexity of a typical report of this type is extra small. Put simply, this is a cheap, throwaway $5 report.

**Saved Ad Hoc Query**. Each customer can have a library of saved Ad Hoc Query reports, which they can run themselves, on demand. These are $5 reports also.

**Summary Report**. This is a panel on a page in the application designed to answer questions about the data through summaries of that data. A summary might be a table that displays counts per status, a time series graph, a frequency distribution chart, a pivot table with multiple row and column dimensions, or some other tabular or visual representation of summary data. Examples can be found throughout the Admin UI.

**Custom Search**. As a general rule, Custom Search reports should be avoided, but the size and complexity here is still small. A typical search page needs about 4h of development time.

**Scheduled Report**. Reports that are especially large and/or computation-intensive must be scheduled to run outside peak business hours. The size and complexity of a Scheduled Report can vary widely, therefore development effort varies widely, and might require anywhere from 5 minutes to 5 days, depending on the details.

**SSRS**. This is a Microsoft SQL Server Reporting Services report. It might be developed for a specific customer, or it might be developed for the core InSite product. Currently, we have SSRS reports for NCSHA and Northern Mat only.

**BI**. This is a Microsoft Power BI report. Microsoft BI is the next evolution of SSRS. We have some customers inquiring about this option; therefore, it is a topic for future research. Currently we have no BI reports.
