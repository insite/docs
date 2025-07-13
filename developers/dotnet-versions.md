---
description: A quick refresher on the various flavours of Microsoft .NET
icon: hashtag
---

# .NET Versions

This document outlines the approach to migrating source code from .NET Framework 4.8 to .NET Standard 2.0 and .NET 9 (Core).

{% embed url="https://versionsof.net" %}

## Dependencies <a href="#dependencies" id="dependencies"></a>

.NET Framework and .NET Core dependencies can be summarized this way:

* You **can** reference a .NET Standard assembly from .NET Framework and from .NET Core.
* You can **not** reference a .NET Core assembly from .NET Framework.
* You **can** reference a .NET Framework assembly from .NET Core.

> .NET Framework does **not** support .NET Standard **2.1** and our .NET Framework assemblies need to reference .NET Standard assemblies. Therefore, we target .NET Standard **2.0** in a library that needs to be used by both .NET Framework and .NET Core.

## Development Tools <a href="#development-tools" id="development-tools"></a>

* Visual Studio 2022 is the recommended IDE for all .NET Framework development work.
* VS Code is the recommended IDE for all React development work.
* Either (or both) tools can be used for .NET Standard and .NET Core development work.
