---
description: "Execute these 3 scripts to setup ASP.NET session state. They are located in the InSite repository under:"
---

# Metadata

## Database Setup <a href="#metadata-databasesetup" id="metadata-databasesetup"></a>

### One-Time Initial Setup <a href="#metadata-one-timeinitialsetup" id="metadata-one-timeinitialsetup"></a>

Execute these 3 scripts to setup ASP.NET session state. They are located in the InSite repository under:

* `<InSiteRepoRoot>\Infrastructure\Scripts\Database\Session State`

1. `Setup-SessionState-1.sql` is executed in SQL Server Management Studio
2. `Setup-SessionState-2.ps1` is executed on a PowerShell command prompt
3. `Setup-SessionState-3.sql` is executed in SQL Server Management Studio

Using SQL Server Management Studio create a new login named `IIS APPPOOL\\InSiteAppPool` if it doesn't exist.

### Restore Database Backup <a href="#metadata-restoredatabasebackup" id="metadata-restoredatabasebackup"></a>

An anonymized backup copy of the database is located in your local backups folder, for example:

* `<LocalBackupsFolder>\Local.bak`

You can use Microsoft SQL Server Management Studio to restore the database.

Alternatively, you can execute a script from PowerShell or from a Windows command prompt. See below for additional instructions.

### Command Line Setup <a href="#metadata-commandlinesetup" id="metadata-commandlinesetup"></a>

Note: If you have already added the PowerShell profile from Local Skip this part.

#### PowerShell setup <a href="#metadata-powershellcommandprompt" id="metadata-powershellcommandprompt"></a>

Edit your PowerShell profile so it includes an alias for the InSite Maintenance console application, plus functions to restore the database from a backup, switch between master and develop databases, and execute SQL upgrade scripts.

Substitute `<InSiteRepoRoot>` and `<LocalBackupsFolder>` for the absolute paths on your machine.

```powershell
$MaintenanceExe = "<InSiteRepoRoot>\Code\Apps\Source\InSite.Maintenance\bin\Debug\InSite.Maintenance.exe"
$UpgradeScripts = "<InSiteRepoRoot>\Code\Apps\Source\InSite.Maintenance\Scripts\Upgrades"
$BackupsFolder  = "<LocalBackupsFolder>"

Set-Alias -Value $MaintenanceExe -Name "insite"

function Sql-Restore { insite restore-databases -b $BackupsFolder }
function Sql-Switch  { insite switch-databases }
function Sql-Mark    { insite mark-scripts    -p $UpgradeScripts }
function Sql-Upgrade { insite upgrade-scripts -p $UpgradeScripts }
```

From a PowerShell command prompt, you can restore two copies of the SQL Server database backup file with this command:

* `Sql-Restore`

To switch between **master** and **develop** copies of the database:

* `Sql-Switch`

#### Windows command-prompt setup <a href="#metadata-windowscommandprompt" id="metadata-windowscommandprompt"></a>

If you prefer the Windows command prompt over PowerShell, create four CMD files. In each one, substitute `<InSiteRepoRoot>` and `<LocalBackupsFolder>` for the absolute paths on your machine.

1. Create four CMD files:
   * **Upgrade.cmd** — runs SQL upgrade scripts.
   * **Mark.cmd** — marks SQL upgrade scripts as executed (use when the script file was already applied during development).
   * **Switch.cmd** — switches from one environment to another (for example, **dev** to **hotfix**).
   * **Restore.cmd** — restores the database backup.
2. Example of **Upgrade.cmd**:

```cmd
"<InSiteRepoRoot>\Code\Apps\Source\InSite.Maintenance\bin\Debug\InSite.Maintenance.exe" upgrade-scripts -p "<InSiteRepoRoot>\Code\Apps\Source\InSite.Maintenance\Scripts\Upgrades"
pause
```

Where **-p** specifies the folder that contains the upgrade scripts.

1. Example of **Mark.cmd**:

```cmd
"<InSiteRepoRoot>\Code\Apps\Source\InSite.Maintenance\bin\Debug\InSite.Maintenance.exe" mark-scripts -p "<InSiteRepoRoot>\Code\Apps\Source\InSite.Maintenance\Scripts\Upgrades"
pause
```

1. Example of **Switch.cmd**:

```cmd
"<InSiteRepoRoot>\Code\Apps\Source\InSite.Maintenance\bin\Debug\InSite.Maintenance.exe" switch-databases
pause
```

1. Example of **Restore.cmd**:

```cmd
"<InSiteRepoRoot>\Code\Apps\Source\InSite.Maintenance\bin\Debug\InSite.Maintenance.exe" restore-databases -b "<LocalBackupsFolder>"
pause
```

Where parameter **-b** points to the folder with backups. The same folder will be used to store database files.\
You can add parameter **-c true** so that the utility restores the database only in the current environment.

### Database Setup <a href="#metadata-databasesetup.1" id="metadata-databasesetup.1"></a>

1. Run **Sql-Restore** or **Restore.cmd**. This will restore the database backup to both `InSite_master` and `InSite_develop` Databases.
2. Run **Sql-Switch** or **Switch.cmd** to switch between develop and master databases. This will work by renaming either of the databases to `InSite` as default database and the other one from `InSite` to its original name.
3. Make sure `InSite_develop` is your default database.
4. Open a new Query in SQL Server Management Studio and run below scripts.

```text
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

```text
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

The infrastructure team just provided the latest backups and I need to restore them.

For this purpose run **Sql-Restore**.

#### Scenario 4. <a href="#metadata-scenario4" id="metadata-scenario4"></a>

I need to switch to **hotfix** for fixing some bugs.

For this purpose do the following steps:

1. Switch Git to **hotfix** branch
2. Run **Sql-Switch**. This command will rename **InSite** to **InSite\_develop** and rename **InSite\_master** to **InSite**
3. Run **Sql-Upgrade** to make sure that the current database has all the latest changes.
4. Do all the required fixes and push them to **hotfix**.
5. Run **Sql-Switch** to switch back to **develop** database. This command will rename **InSite** to **InSite\_master** and rename **InSite\_develop** to **InSite**
6. Switch Git to **develop** branch.
