# Command-Line Interface

## Overview

- The .NET CORE CLI is a tool for creating, restoring packages, building, running and publishing .NET applications;
- Visual Studio internally uses this CLI to restore, build and publish an application;

## Command Structure

- Syntax:
  - `dotnet <command> <argument> <option>`;

## Basic Commands

- new:
  - Creates a new project, configuration file, or solution based on the specified template;
- restore:
  - Restores the dependencies and tools of a project;
- build:
  - Builds a project and all of its dependencies;
- run:
  - Runs source code without any explicit compile or launch commands;
- publish:
  - Packs the application and its dependencies into a folder for deployment to a hosting system;
- test:
  - executes unit tests;
- vtest:
  - Runs tests from specified files;
- pack:
  - Packs the code into a NuGet Package;
- clean:
  - Cleans the output of a project;
- sln:
  - Modifies the .NET Core solution file;
- help:
  - Display help for a specified command;
- store:
  - Stores the specified assemblies in the runtime package store;

## Project Modification Commands

- add package:
  - Adds a package reference to a project;
- add reference:
  - Adds project-to-project (P2P) references;
- remove package:
  - Removes package reference from the project;
- remove reference:
  - Removes project reference;
- list reference:
  - Lists all project-to-project references;

## Advanced commands

- nuget delete:
  - Deletes or unlists a package from the server;
- nuget locals:
  - Clears or lists local NuGet resources;
- nuget push:
  - Pushes a package to the server and publishes it;
- msbuild:
  - Builds a project and all of its dependencies;
- dotnet install script:
  - Script used to install the .NET Core CLI tools and the shared runtime;

## Create a New Project

- The following creates new console project in the current directory with the same name as current directory:
  - `dotnet new console`;
- The following command creates a new console project named MyConsoleApp. The -n or --name option species the name of a project:
  - `dotnet new console -n MyConsoleApp`;
- The following command creates a new console application named MyConsoleApp to MyProjects directory. The -o or --output option is used to specify an output directory where the project should be generated:
  - `dotnet new console -n MyConsoleApp -o C:\MyProjects`;

### Add Package Reference

- `dotnet add package <packgae_name>`;

### Restore Packages

- `dotnet restore`;

### Build Project

- `dotnet build`;

### Run Project

- `dotnet run`;

## Getting Help

- We can get help on any .NET Core CLI commands by typing -h or -help at the end of the command we want to get help on;

## Links

- <https://www.tutorialsteacher.com/core/net-core-command-line-interface;>
