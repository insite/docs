# Metadata

## Database Setup <a href="#metadata-databasesetup" id="metadata-databasesetup"></a>

### One-Time Initial Setup <a href="#metadata-one-timeinitialsetup" id="metadata-one-timeinitialsetup"></a>

Execute these 3 scripts to setup ASP.NET session state:

* `C:\\Base\\Repos\\InSite\\Infrastructure\\Scripts\\Database\\Session State`

1. `Setup-SessionState-1.sql` is executed in SQL Server Management Studio
2. `Setup-SessionState-2.ps1` is executed on a PowerShell command prompt
3. `Setup-SessionState-3.sql` is executed in SQL Server Management Studio

Using SQL Server Management Studio create a new login named `IIS APPPOOL\\InSiteAppPool` if it doesn't exist.

### Restore Database Backup <a href="#metadata-restoredatabasebackup" id="metadata-restoredatabasebackup"></a>

An anonymized backup copy of the database is located here:

* C:\Base\Data\Databases\Backups\Local.bak

You can use Microsoft SQL Server Management Studio to restore the database.

Alternatively, you can execute a script from PowerShell or from a Windows command prompt. See below for additional instructions.

### Command Line Setup <a href="#metadata-commandlinesetup" id="metadata-commandlinesetup"></a>

Note: If you have already added the PowerShell profile from Local Skip this part.

#### PowerShell Command Prompt (Dan) <a href="#metadata-powershellcommandprompt-dan" id="metadata-powershellcommandprompt-dan"></a>

Edit your PowerShell profile so it includes an alias for the InSite Maintenance console application, and so it includes functions to restore the database from a backup, switch between master and develop databases, execute SQL upgrade scripts.

```
Set-Alias -Value "C:\\Base\\Repos\\InSite\\Code\\Apps\\Source\\InSite.Maintenance\\bin\\Debug\\InSite.Maintenance.exe" -Name "insite"

function Sql-Restore { insite restore-databases -b C:\\Base\\Data\\Databases\\Backups }
function Sql-Switch  { insite switch-databases }
function Sql-Mark    { insite mark-scripts      -p C:\\Base\\Repos\\InSite\\Code\\Apps\\Source\\InSite.Maintenance\\Scripts\\Upgrades }
function Sql-Upgrade { insite upgrade-scripts   -p C:\\Base\\Repos\\InSite\\Code\\Apps\\Source\\InSite.Maintenance\\Scripts\\Upgrades }
```

From a PowerShell command prompt, you can restore two copies of the SQL Server database backup file with this command:

* `Sql-Restore`

To switch between **master** and **develop** copies of the database:

* `Sql-Switch`

#### Windows Command Prompt (Aleksey) <a href="#metadata-windowscommandprompt-aleksey" id="metadata-windowscommandprompt-aleksey"></a>

1. Create four CMD files:
   * Upgrade.cmd. This command should be used to run SQL upgrade scripts
   * Mark.cmd. This command should be used to mark SQL upgrade scripts as executed in case the script file(s) already was applied during development.
   * Switch.cmd. Switch from one environment to another, for example, from **dev** to **hotfix**.
   * Restore.cmd. Restore the database backup.
2. Example of **Upgrade.cmd**

```
C:\\Base\\Repos\\InSite\\Code\\Apps\\Source\\InSite.Maintenance\\bin\\Debug\\InSite.Maintenance.exe upgrade-scripts -p D:\\Projects\\InSite\\Repos\\Code\\Apps\\Source\\InSite.Maintenance\\Scripts\\Upgrades
pause
```

Where **-p** specifies where upgrade scripts located

1. Example of **Mark.cmd**

```
C:\\Base\\Repos\\InSite\\Code\\Apps\\Source\\InSite.Maintenance\\bin\\Debug\\InSite.Maintenance.exe mark-scripts -p C:\\Base\\Repos\\InSite\\Code\\Apps\\Source\\InSite.Maintenance\\Scripts\\Upgrades
pause
```

1. Example of **Switch.cmd**

```
C:\\Base\\Repos\\InSite\\Code\\Apps\\Source\\InSite.Maintenance\\bin\\Debug\\InSite.Maintenance.exe switch-databases
pause
```

1. Example of **Restore.cmd**

```
C:\\Base\\Repos\\InSite\\Code\\Apps\\Source\\InSite.Maintenance\\bin\\Debug\\InSite.Maintenance.exe restore-databases -b C:\\Base\\Data\\Databases\\Backups
pause
```

Where parameter **-b** points to the folder with backups. The same folder will be used to store database files.\
You can add parameter **-c true** so that the utility restores the database only in the current environment.

### Database Setup <a href="#metadata-databasesetup.1" id="metadata-databasesetup.1"></a>

1. Run **Sql-Restore** or **Restore.cmd**. This will restore the database backup to both `InSite_master` and `InSite_develop` Databases.
2. Run **Sql-Switch** or **Switch.cmd** to switch between develop and master databases. This will work by renaming either of the databases to `InSite` as default database and the other one from `InSite` to its original name.
3. Make sure `InSite_develop` is your default database.
4. Open a new Query in SQL Server Management Studio and run below scripts.

```
USE master;
GO
EXEC sp_configure 'clr enabled' ,1
GO
RECONFIGURE
GO

USE InSite
GO
EXEC sp_changedbowner 'sa'
GO
ALTER DATABASE InSite SET TRUSTWORTHY ON;
GO
```

1. Run **Sql-Upgrade** or **Upgrade.cmd** to apply all the latest upgrade scripts.
2. Run below queries to create a default user.

```
use InSite
go

UPDATE identities.[User] SET UserPasswordExpired = DATEADD(yy, 1, getdate()), UserPasswordHash = '1000:pnz5kpWsT5Nwh4RL1tPLsxlAAT69DXN3:mYT6XDvR0yWxEaBd+LJsKUI329qANQJH'
GO

UPDATE identities.[User] SET 
  Email = 'developer@insite.com'
, FirstName = 'Thomas'
, MiddleName = 'A.'
, LastName = 'Anderson'
, FullName = 'Thomas Anderson'
, UserPasswordHash = '1000:3fxs4wtoCPQRUVGC3V+Dh1YuIbG8Ztmu:EuppFuptl3kOl4i7ko+S9zE3jvVGbpvy'
, UserPasswordExpired = 'Dec 31, 2022'
WHERE 
  UserIdentifier = 'C43357BE-B96F-42EB-ACE6-B4419D523C9A';
GO
```

Now your environment is ready.

### Different scenarios of commands usages. <a href="#metadata-differentscenariosofcommandsusages" id="metadata-differentscenariosofcommandsusages"></a>

#### Scenario 1. <a href="#metadata-scenario1" id="metadata-scenario1"></a>

I just "pulled" the latest sources and need to apply all the latest scripts to my current database.

For this purpose run **Sql-Upgrade**.

#### Scenario 2. <a href="#metadata-scenario2" id="metadata-scenario2"></a>

I create some script and already applied it to the database therefore I don't want it to be run again by Sql-Upgrade.

For this purpose run **Sql-Mark**

#### Scenario 3. <a href="#metadata-scenario3" id="metadata-scenario3"></a>

Dan just provided the latest backups and I need to restore them.

For this purpose run **Sql-Restore**

#### Scenario 4. <a href="#metadata-scenario4" id="metadata-scenario4"></a>

I need to switch to **hotfix** for fixing some bugs.

For this purpose do the following steps:

1. Switch Git to **hotfix** branch
2. Run **Sql-Switch**. This command will rename **InSite** to **InSite\_develop** and rename **InSite\_master** to **InSite**
3. Run **Sql-Upgrade** to make sure that the current database has all the latest changes.
4. Do all the required fixes and push them to **hotfix**.
5. Run **Sql-Switch** to switch back to **develop** database. This command will rename **InSite** to **InSite\_master** and rename **InSite\_develop** to **InSite**
6. Switch Git to **develop** branch.
