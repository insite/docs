---
description: How to run a dynamic SQL query from the admin reports area
---

# Queries

## Dynamic SQL Query

Go to: (depending on the environment):

* [https://global.insite.com/admin/reports/queries/sql](https://global.insite.com/admin/reports/queries/sql)
* [https://sandbox-global.insite.com/admin/reports/queries/sql](https://sandbox-global.insite.com/admin/reports/queries/sql)
* [https://dev-global.insite.com/admin/reports/queries/sql](https://dev-global.insite.com/admin/reports/queries/sql)

You should see something like this:

<figure><img src="../../.gitbook/assets/queries-01.png" alt="Queries 01"><figcaption></figcaption></figure>

In the large Text Area insert the SQL Code:

<figure><img src="../../.gitbook/assets/queries-02.png" alt="Queries 02"><figcaption></figcaption></figure>

And click Execute

<figure><img src="../../.gitbook/assets/queries-03.png" alt="Queries 03"><figcaption></figcaption></figure>

Results for the SQL Query will display in the Results panel.

<figure><img src="../../.gitbook/assets/queries-04.png" alt="Queries 04"><figcaption></figcaption></figure>

If you scroll right you will notice column names:

<figure><img src="../../.gitbook/assets/queries-05.png" alt="Queries 05"><figcaption></figcaption></figure>

To download the Query results, click on the **Download** button in the **Results** panel.

### Example: Assessment Attempts

```sql
select * from logs.Change where AggregateIdentifier = 'INSERT ASSESSMENT ATTEMPT UNIQUE IDENTIFIER' order by changetime desc
```

OR

```sql
select * from logs.Change where AggregateIdentifier = 'INSERT ASSESSMENT ATTEMPT UNIQUE IDENTIFIER'
```

<figure><img src="../../.gitbook/assets/queries-06.png" alt="Queries 06"><figcaption></figcaption></figure>
