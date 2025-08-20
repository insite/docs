---
description: A few important details about the Microsoft .NET platform
icon: hashtag
---

# .NET

## Versions

We use each of these versions of .NET for specific purposes:

* [.NET Framework 4.8](https://versionsof.net/framework/4.8.1/)
* [.NET Standard 2.0](https://learn.microsoft.com/en-us/dotnet/standard/net-standard?tabs=net-standard-2-0)
* [.NET Core 9.0](https://versionsof.net/core/9.0/)

### Dependencies <a href="#dependencies" id="dependencies"></a>

.NET Framework and .NET Core dependencies can be summarized this way:

* You <mark style="color:$success;">**can**</mark> reference a .NET Standard assembly from .NET Framework and from .NET Core.
* You can <mark style="color:$danger;">**not**</mark> reference a .NET Core assembly from .NET Framework.
* You <mark style="color:$success;">**can**</mark> reference a .NET Framework assembly from .NET Core.

> .NET Framework does **not** support .NET Standard **2.1** and our .NET Framework assemblies need to reference .NET Standard assemblies. Therefore, we target .NET Standard **2.0** in a library that needs to be used by both .NET Framework and .NET Core.

## Development Tools <a href="#development-tools" id="development-tools"></a>

* Visual Studio 2022 is the recommended IDE for all .NET Framework development work.
* VS Code is the recommended IDE for all React development work.
* Either (or both) tools can be used for .NET Standard and .NET Core development work.
