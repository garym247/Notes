# dotnet --version
Displays the version of dotnet.

# dotnet new
Creates a new project from the given template.

## dotnet new
Lists all the available templates for creating a project

## dotnet new console -n "HelloWorld"
* Creates a console application
* The "-n" option names the project "HelloWorld".

## dotnet new blazorwasm -n "BlazorHelloWorld"
*Creates a client-side Blazor application.

## dotnet new sln -n "HellowWorldSolution"
* Creates an empty solution file.

## dotnet new sln -n \<solution name>
* Don't need add the .sln file extension, VS Code automatically adds it.
* Note: Enclose \<solution name> in quotes if it contains spaces.

## dotnet new \<template> -n \<project name>
* don\'t need to add .csproj extenstion, VS code will do it automatically.
* VS Code automatically creates a sub-directory for the project.
* possible values for \<template>, console, wpf, classlib, etc

# dotnet sln
## dotnet sln \<solution name>.sln add \<project name>.csproj
* e.g. dotnet sln patterns.sln add policy\\policy.csproj

## dotnet \<project name>.csproj reference \<project name>.csproj

Hint: open each project directory with VS Code (e.g. code \<project
path>), so that VS Code will automatically create .vscode\\launch.json
and .vscode\\tasks.json files for each project.

# dotnet build

# dotnet watch build

# dotnet run
* By default, it builds the Debug configuration of the project.
* To build the Release configuration: dotnet run -c Release

# dotnet add package

# dotnet list

## dotnet list package
Lists all the package references used by a project

## dotnet list package --outdated
Lists the outdated packages

## dotnet list reference

# dotnet publish
* -c publishes the specified [c]{.underline}onfiguration
* -o specifies the [o]{.underline}utput directory

# dotnet restore
