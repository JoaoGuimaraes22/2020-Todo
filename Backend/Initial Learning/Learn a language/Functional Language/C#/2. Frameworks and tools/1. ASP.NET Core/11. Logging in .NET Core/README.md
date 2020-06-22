# Fundamentals of Logging in .NET Core

## Overview

- The .NET Core SDK is a light weight SDK which includes a bare minimum set of features required to build an application;
- We can install NuGet packages for other features we require for our application;

- For this, Microsoft provides .NET APIs as .NET Extensions;
- .NET Extensions is an open-source, cross-platform set of APIs for commonly used programming patterns and utilities, such as dependency injection, logging, and app configuration;
- Most APIs in this project are meant to work on many .NET platforms, such as .NET Core, .NET Framework, Xamarin, and others;
- While commonly used in ASP.NET Core applications, these APIs are not coupled to the ASP.NET Core application model;
- They can be used in console apps, WinForms and WPF, etc.;
- You can find the documentation and the source code of extensions at https://github.com/aspnet/Extensions;

- All the extensions are included under the `Microsoft.Extensions` namespace;
- You can find all built-in and third party extensions at nuget.org/packages.

- The Logging API is included in the `Microsoft.Extensions.Logging` package;
- The Logging API does not work as standalone;
- It works with one or more logging providers that store or display logs to a particular medium such as Console, Debug, TraceListeners etc.
- There are two important building blocks for implementing logging in a .NET Core based application:

  - Logging API;
  - Logging Providers.

- The logging API in `Microsoft.Extensions.Logging` works on the .NET Core based applications whether it is ASP.NET Core or EF Core;
- You just need to use the logging API with one or more logging providers to implement logging in any .NET Core based application

## Logging API

- Microsoft provides logging API as an extension in the wrapper `Microsoft.Extensions.Logging` which comes as a NuGet package;
- `Microsoft.Extensions.Logging` includes the necessary classes and interfaces for logging;
- The most important are the ILogger, ILoggerFactory, ILoggerProvider interfaces and the LoggerFactory class.

## ILoggerFactory

- The `ILoggerFactory` is the factory interface for creating an appropriate `ILogger` type instance and also for adding the `ILoggerProvider` instance;
- For example:

```c#
public interface ILoggerFactory : IDisposable
{
    ILogger CreateLogger(string categoryName);
    void AddProvider(ILoggerProvider provider);
}
```

- The Logging API includes the built-in `LoggerFactory` class that implements the `ILoggerFactory` interface;
- We can use it to add an instance of type `ILoggerProvider` and to retrieve the `ILogger` instance for the specified category;
- Visit <https://docs.microsoft.com/en-us/dotnet/api/microsoft.extensions.logging.iloggerfactory?view=dotnet-plat-ext-3.1> and <https://docs.microsoft.com/en-us/dotnet/api/microsoft.extensions.logging.loggerfactory?view=dotnet-plat-ext-3.1> for more information.

## ILoggerProvider

- The `ILoggerProvider` manages and creates an appropriate logger, specified by the logging category;
- For example:

```c#
public interface ILoggerProvider : IDisposable
{
    ILogger CreateLogger(string categoryName);
}
```

- We can create our own logging provider by implementing the `ILoggerProvider` interface;
- Visit <https://docs.microsoft.com/en-us/dotnet/api/microsoft.extensions.logging.iloggerprovider?view=dotnet-plat-ext-3.1> for more information.

## ILogger

- The `ILogger` interface includes methods for logging to the underlying storage;
- There are many extension methods which make logging easy;
- For example:

```c#
public interface ILogger
{
    void Log<TState>(LogLevel logLevel, EventId eventId, TState state, Exception exception, Func<TState, Exception, string> formatter);
    bool IsEnabled(LogLevel logLevel);
    IDisposable BeginScope<TState>(TState state);
}
```

- Visit ILogger for more information.

## Logging Providers

- A logging provider displays or stores logs to a particular medium such as a console, a debugging event, an event log, a trace listener, and others;
- Microsoft provides various logging providers as NuGet packages;
- The following lists important logging providers and they're respective output Target:

  - `Microsoft.Extensions.Logging.Console`:
    - Console;
  - `Microsoft.Extensions.Logging.AzureAppServices`:
    - Azure App Services 'Diagnostics logs' and 'Log stream' features;
  - `Microsoft.Extensions.Logging.Debug`:
    - Debugger Monitor;
  - `Microsoft.Extensions.Logging.EventLog`:
    - Windows Event Log;
  - `Microsoft.Extensions.Logging.EventSource`:
    - EventSource/EventListener;
  - `Microsoft.Extensions.Logging.TraceSource`:
    - Trace Listener;

- Microsoft has also collaborated with various logging framework teams (including third parties like NLog, Serilog, Loggr, Log4Net, and others) to extend the list of providers compatible with Microsoft.Extensions.Logging;

## Console Logging Provider

- Displays logs on the console using the NuGet package for a console provider;
- The `Microsoft.Extensions.Logging.Console` package includes logging classes which send log output to the console;
- The `ConsoleLogger` implements `ILogger`, while the `ConsoleLoggingProvider` implements `ILoggingProvider`;
- The `ConsoleLoggerExtensions` class includes extension method `AddConsole()`, which adds a console logger to the `LoggerFactory`.

## Learn how to display logs on the Console in a .NET Core console application

- Create a new console application using the Console App (.NET Core) template in Visual Studio;
- Install the NuGet package of `Microsoft.Extensions.Logging`;
- You can install it either using the NuGet Package Manager or executing the following command in the Package Manager Console: `Install-Package Microsoft.Extensions.Logging`;
- Install a logging provider of your choice;
- Here, we will send logs on the Console, so, install the `Microsoft.Extensions.Logging.Console` package either using NPM or execute the following command in the Package Manager Console in Visual Studio: `Install-Package Microsoft.Extensions.Logging.Console`;
- After successfully installing the above two packages, you can now implement logging in your .NET Core console application, as shown below:

```c#
namespace DotnetCoreConsoleApp
{
    class Program
    {
        static void Main(string[] args)
        {
            ILoggerFactory loggerFactory = new LoggerFactory(
                            new[] { new ConsoleLoggerProvider((_, __) => true, true) }
                        );
            //or
            //ILoggerFactory loggerFactory = new LoggerFactory().AddConsole();

            ILogger logger = loggerFactory.CreateLogger<Program>();
            logger.LogInformation("This is log message.");
        }
    }
}
```

- Outputs: info: DotnetCoreConsoleApp.Program[0]
  This is log message.

- In the above example, we created an object of the `LoggerFactory` class and assigned it to the `ILoggerFactory` type variable, as shown below.

```c#
ILoggerFactory loggerFactory = new LoggerFactory(
    new[] { new ConsoleLoggerProvider ((_, __) => true, true) }
);
```

- The `LoggerFactory` can contain one or more logging providers, which can be used to log to multiple mediums concurrently;
- The constructor of the LoggerFactory accepts an array of different logger provider objects as `new[] { }`;
- We want to display logs on the console, so we need to create an object of the console logger provider `ConsoleLoggerProvider`;
- There are four constructors of the `ConsoleLoggerProvider`;
- Use the one that allows lambda expression (Func<>) for log filtration and includeScope Boolean;
- Here, we don't want to filter any information so the lambda expression would always return true `(_, __) => true`, as shown below:

```c#
new ConsoleLoggerProvider((_, __) => true, true)
```

- Then, we can use this object of the `LoggerFactory` to create a logger using which we can actually log information, errors, warnings, traces, debugs etc.;
- `loggerFactory.CreateLogger<Program>()` creates a logger specific to the `Program` class so that the logger will display a message with context info, e.g. DotnetCoreConsoleApp.Program[0];
- Most logging providers include an extension method of `ILoggerFactory`, which is a shortcut to add a provider to the logger factory;
- For example, to add a console logger provider to the LoggerFactory, just call the `LoggerFactory.AddConsole()` extension method with the same parameters as ConsoleLoggerProvider, as shown below:

```c#
public ILoggerFactory loggerFactory = new LoggerFactory().AddConsole();
```

- This is more readable and maintainable than creating a logger provider manually and serves the same purpose;

## Log Levels

- Log levels indicate the importance or severity of log messages;
- Built-in log providers include extension methods to indicate log levels;
- The following lists log levels in .NET Core:
  - Trace;
  - Debug;
  - Information;
  - Warning;
  - Error;
  - Critical;

-We can use extension methods to indicate the level of the log messages as shown below:

```c#
namespace DotnetCoreConsoleApp
{
    class Program
    {
        static void Main(string[] args)
        {
            ILoggerFactory loggerFactory = new LoggerFactory().AddConsole((_, __) => true);
            ILogger logger = loggerFactory.CreateLogger<Program>();

            logger.LogInformation("Logging information.");
            logger.LogCritical("Logging critical information.");
            logger.LogDebug("Logging debug information.");
            logger.LogError("Logging error information.");
            logger.LogTrace("Logging trace");
            logger.LogWarning("Logging warning.");
        }
    }
}
```

- Visit <https://docs.microsoft.com/en-us/archive/msdn-magazine/2016/april/essential-net-logging-with-net-core> for more detailed information.

## Links

- <https://www.tutorialsteacher.com/core/fundamentals-of-logging-in-dotnet-core> ;
