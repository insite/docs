# Database naming conventions

{% hint style="info" %}
Some of the naming conventions here are new, and some are revised from old/existing conventions. Existing code and existing database objects are **not** expected to follow these conventions perfectly. New code and new database objects should follow these conventions.
{% endhint %}

## Databases

* The name of a database is a hybrid of Pascal case and snake case.\
  **Partition\_Environment\_Application**
* Examples:
  * E00\_Development\_Engine
  * E02\_Sandbox\_Shift
  * E05\_Production\_Shift

## Schemas

* The name of a schema is lowercase and singular form.
* A schema name should match a component (toolkit) name.
* Examples:
  * billing
  * platform

## Tables

* T = The name of a base **Table** (i.e., a non-projection table) has a `T` prefix. A base table stores raw, unprojected data.
* P = The name of a **Projection** table (also called a **Query** table) has an `R` prefix (or a `Q` prefix). A projection table stores a projection of data from a base table.
* B = The name of a temporary **Buffer** table has a `B` prefix. A buffer table caches intermediate results for complex multi-stage algorithms, queries, and reports.
* Z = The name of deprecated **Zombie** table has a `Z` prefix. A zombie table is a candidate for removal or replacement.
* The name of a table name is singular Pascal case (i.e. the first letter of each word in a compound word is capitalized).
* Examples:
  * Good: TUser, BComplexReportPreparation
  * Bad: User, Users, TUsers

## Views

* The name of a view has a `V` prefix.
* The name of an indexed view has an `X` prefix.
* The name of a view is singular Pascal case.
* Examples:
  * VOrganizationDetail
  * XFastInventorySummary

{% hint style="warning" %}
This is a question for future discussion: \
Should the name of a view follow the naming convention for a query?
{% endhint %}

## Stored Procedures

* The name of a stored procedure follows the naming convention for queries and commands.
* If it is not possible to follow the naming convention for queries and commands, then the name of a stored procedure has a `P` prefix.

## Columns

* The name of a column is Pascal case.
* Ideally, a column name should be unique.
  * If two different tables contain a column with the same name, then both columns should have the same meaning.
  * If two different columns have different meanings then they should have different names.
  * For example, TUser.FullName and TPerson.FullName may be acceptable, but TUser.Name and TModule.Name is not recommended because a person’s full name is not semantically equivalent to a module's name. Therefore, TUser.FullName and TModule.ModuleName are better column names.
* The name of a column that stores an email notification message identifier should follow this convention:
  * **When** \<ChangeType> **Notify** \<RecipientDescriptor> **MessageIdentifier**
  * For example: WhenCrazyWidgetColorChangedNotifyMyImaginaryFriendsInGreenlandMessageIdentifier
  * Notice the terms **When**, **Notify**, and **MessageIdentifier** can be used (if needed) to parse the ChangeType and/or RecipientDescriptor from this type of a column name.

### Data Types

* If a date/time column contains both a Date part and a Time part then the data type must be DATETIMEOFFSET to ensure the meaning of its values is unambiguous with regard to time zone.
* If a date/time column contains a Date part only then the data type must be DATE.
* If a date/time column contains a Time part only then the data type must be TIME.

## Entity Framework

* The name of an entity class should match the name of the database table (or view) to which it binds, with the suffix "Entity".
  * For example, if an entity class binds to a database table named TRole, then the C# entity class should be named TRoleEntity
* The name of an entity type configuration class should match the name of the database table (or view) to which it binds, with the suffix "Configuration".
  * For example, TRoleConfiguration.
* The name of a DbSet\<T> property within a DbContext class should exactly match the name of the database table (or view) to which it binds.
  * For example, if a DbContext contains a property of type DbSet\<TOrganizationEntity>, which binds to the database table named QOrganization, then the name of the property should be QOrganization:\
    internal DbSet\<OrganizationEntity> QOrganization { get; set; }

## SQL Server versus PostgreSQL

The naming conventions above are intended for SQL Server databases, and are **not** a good fit for PostgreSQL databases.

PostgreSQL automatically applies lowercase to object names, therefore upper case letters are **strongly discouraged**.&#x20;

For details, refer to this article: [Do not use upper case table or column names in PostgreSQL](https://wiki.postgresql.org/wiki/Don't_Do_This#Don.27t_use_upper_case_table_or_column_names).

Snake case is **strongly recommended** for object names in PostgreSQL databases.

A separate list of conventions will be documented here when time permits.
