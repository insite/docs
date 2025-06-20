---
icon: hashtag
---

# .NET Versions

This document outlines the approach to migrating source code from .NET Framework 4.8 to .NET Standard 2.0 and .NET 9 (Core).

{% embed url="https://versionsof.net" %}

### Dependencies <a href="#dependencies" id="dependencies"></a>

.NET Framework and .NET Core dependencies can be summarized this way:

* You **can** reference a .NET Standard assembly from .NET Framework and from .NET Core.
* You can **not** reference a .NET Core assembly from .NET Framework.
* You **can** reference a .NET Framework assembly from .NET Core.

> .NET Framework does **not** support .NET Standard **2.1** and our .NET Framework assemblies need to reference .NET Standard assemblies. Therefore, we target .NET Standard **2.0** in a library that needs to be used by both .NET Framework and .NET Core.

### Conventions <a href="#conventions" id="conventions"></a>

* .NET Framework assemblies are named with one of these prefixes: **InSite, Polaris**
* .NET Standard and .NET Core assemblies are named with one of these prefixes: **Shift, Engine, Tek, Arc**
* React applications are named with this prefix: **Shift, Tek, Arc**

New libraries, APIs, and console applications target .NET Core or .NET Standard.

New web applications target React.

#### Optional Conventions (proposed for future consideration) <a href="#optional-conventions-proposed-for-future-consideration" id="optional-conventions-proposed-for-future-consideration"></a>

* Applications and libraries that target .NET Standard are organized under `[Repo]\src`.
* Applications and libraries that target .NET Core are organized under `[Repo]\src`.
* Applications and libraries that target .NET Framework are organized under `[Repo]\Source`.

### .NET Framework Migration Approach <a href="#net-framework-migration-approach" id="net-framework-migration-approach"></a>

> The InSite (.UI) web application is a .NET Framework [ASP.NET](http://asp.net/) Web Forms application, and will remain so. The long-term goal is to replace ASPX web forms with React. This implementation will be done in the Shift.UI project.

Whenever time and opportunity permit, source code is moved from an **InSite** library to a **Shift** library (or a **Tek** library, or an **Arc** library.

Here is the proposed high-level, long-term approach to the overall migration of .NET Framework source code (excluding InSite UI source code):

* Shift.Api handles all Timeline commands and all database access. (Eventually!)
* InSite.Application classes move to Shift.Service, where all commands, interfaces, and subscribers are stored in a subfolder that looks this (for example): Assessments\Banks\\**Process**.
  * Command classes can be moved from Shift.Service to Shift.Contract if/when we want to allow this.
* InSite.Domain classes move to Shift.Service, where all changes, interfaces, and models are stored in a subfolder that looks this (for example): Assessments\Banks\\**State**.
* InSite.Persistence classes move to Shift.Service, where all commands, interfaces, and subscribers are stored in a subfolder that looks this (for example): Assessments\Banks\\**Data**.
* InSite.Common classes move to Shift.Toolbox. If the class to be moved has no dependencies on third-party libraries then it is a candidate for general-purpose reuse, and is therefore a candidate for one of the Tek libraries.
* InSite.Configuration classes move to Shift.Service, which is referenced by Shift.Api, Shift.Terminal, Shift.Test, and Shift.Lab.
* InSite.Maintenance classes move to Shift.Terminal.
* InSite.Tests.Auto classes move to Shift.Test.
* InSite.Lab classes move to Shift.Lab.

### Development Tools <a href="#development-tools" id="development-tools"></a>

* Visual Studio 2022 is the recommended IDE for all .NET Framework development work.
* VS Code is the recommended IDE for all React development work.
* Either (or both) tools can be used for .NET Standard and .NET Core development work.
