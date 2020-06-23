# .NET Core Application Types

## Overview

- We can create two types of applications in .NET Core:
  - Portable Application,
  - Self-contained application;

## Portable Application

- Portable applications are applications which expect .NET Core runtime on the deployment machines;
- They cannot be ran on a machine which does not have .NET Core runtime installed.

## Self-contained Application

- Self-contained applications are applications which include .NET Core runtime when we publish them;
- They can run on a machine which does not have .NET Core runtime installed.

## Configure Application Type

- We can configure ASP.NET Core application as portable or self-contained application using `type` property of`Microsoft.NETCore.App`dependency in`project.json`;
- The "type":"platform" indicates that this application expects .NET Core on the machine;
- This makes it a portable application:

```json
"dependencies": {
    "Microsoft.NETCore.App":{
        "version": "1.0.1",
        "type": "platform"
    },
    // Others ...
}
```

- For the self-contained application, remove type-platform from the dependency;
- This makes it a self-contained application which means .NET Core will be included when you build and publish an application.

## Links

- <https://www.tutorialsteacher.com/core/dotnet-core-application-types> ;
