# Migrate .Net Framework to .Net Core

The "try-convert" tool migrates the .Net Framework project to .Net Core application. Microsoft provides multiple tools for conversion between different frameworks.

This article demonstrates how to convert a Console Application from .Net Framework to .Net Core.

Live Demo Steps for Migration


![](https://miro.medium.com/max/700/1*m5YHJD7X-RVrE3avF8apAg.gif)

Prerequisites
=============

Microsoft launched a dedicated extension to visualize or check if your application is portable to the other .Net Frameworks.

Check the below article on how to install and use the .Net Portability Analyzer.

[Is your application Portable ?](https://medium.com/@singhsukhpinder/is-your-application-portable-98ed14c3d3a6)

Getting Started
===============

Create a simple .Net Framework HelloWorld application from Visual Studio or Download the sample Github project

[.Net Framework Repo](https://github.com/ssukhpinder/HelloWorldDotNetFramework)<br/>
[.Net Core SDK](https://dotnet.microsoft.com/download)
```
Install the new tool via Dotnet SDK from the command line.

dotnet tool install -g try-convert
```

try-convert tool options
------------------------

```
-p, --project <p>
The path to a project to convert

-w, --workspace <w>
The solution or project file to operate on. If a project is not specified, the command will search the current directory for one.

-m, --msbuild-path <m>
The path to an MSBuild.exe, if you prefer to use that

--target-framework, -tfm <tfm>
The name of the framework you would like to upgrade to. If unspecified, the default TFM chosen will be the highest available one found on your machine.

--preview
Use preview SDKs as part of conversion

--diff-only
Produces a diff of the project to convert; no conversion is done

--no-backup
Converts projects and does not create a backup of the originals.

--keep-current-tfms
Converts project files but does not change any TFMs. If unspecified, TFMs may change.
```

Let's start
==========================

Go to .Net Framework project directory where the ".csproj" file exists and open a command prompt session in Administrator mode.

Firstly, .Net Framework gets converted into .Net Standard SDK, and from there, it's turned into .Net Core framework.

Command to convert to .Net Standard
-----------------------------------

The below command will generate a new ".csproj" file of .Net standard type, whereas keeping the backup of .Net Framework file.

### Project structure before migration: Targets 4.7 version

![](https://miro.medium.com/max/690/1*apIfRG-7JS_VRCy6OvupVg.png)

By default, backup is enabled but overridden using no backup option.
```
try-convert -p HelloWorldDotNetFramework.csproj
```

Project structure after migration: .Net Standard

An additional ".csproj" file will be created, and the previous file is renamed.

![](https://miro.medium.com/max/660/1*G7yaiUHcU0luj4DsXDuyjw.png)

If you need to revert the migration changs, delete the newly created ".csproj" file and rename the file ending with the ".old" extension i.e., remove the ".old" extension from filename.

Convert to .Net Core Framework
------------------------------

Open the ".csproj" file in the editor and manually change the tagertFrameworkVersion to .Net Core version installed in local.

![](https://miro.medium.com/max/700/1*PZY9OSCxhT3KxMd15WW2LQ.png)

Save the file, run following commands in sequence.
```
dotnet build
dotnet run
```
If not sure about packages involved during migration, run below command to generate a detailed report before migration.
```
try-convert --diff-only
```