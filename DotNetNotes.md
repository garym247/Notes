.NET platform can be used to build the following types of applications:
* desktop
* web
* cloud
* mobile
* gaming
* IoT
* AI

.NET Framework

.NET Core all combined into .NET

mono/xamarin

.NET Core supports the following OSs:
* Windows
* Linux
* MacOS

WinForms and WPF are specific to the Windows OS, hence they won't be
available for Linux and MacOS.

.NET has the following benefits:
* single SDK
* one BCL (base class library)
* unified toolchain

+-------------------+-----------------+-------------------------------+
| **.NET version**  | **Release       | **Long Term Support?**        |
|                   | Date**          |                               |
|                   |                 | **(means 3 years support)**   |
+===================+=================+===============================+
| 3.1               | Dec 2019        | Yes                           |
+-------------------+-----------------+-------------------------------+
| 5.0               | Nov 2020        | No                            |
+-------------------+-----------------+-------------------------------+
| 6.0               | Nov 2021        | Yes                           |
+-------------------+-----------------+-------------------------------+
| 7.0               | Nov 2022        | No                            |
+-------------------+-----------------+-------------------------------+
| 8.0               | Nov 2023        | Yes                           |
+-------------------+-----------------+-------------------------------+

CLR is C#'s equivalent of the Java Virtual Machine.

# nuget

nuget is a package manager (see nuget.org)

# Visual Studio Projects

Differences between .NET Framework and .NET Core projects:
* .NET Core projects have a "dependencies", .NET Framework projects have a "references" folder
* .NET Core projects have a wwwroot folder
* .NET Core projects have an appsettings.json, .NET Framework projects have a web.config (xml) file

Authentication in an application

Can use Azure Key Vault

CDN = Content Delivery Network

ASP.NET Core uses bootstrap version 4.

Dapper is an alternative to Entity Framework.
