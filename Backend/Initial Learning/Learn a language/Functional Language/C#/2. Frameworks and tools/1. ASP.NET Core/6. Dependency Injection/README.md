# Dependency Injection

## Here you will learn about

1. Dependency Injection:
   1. Built-in IoC Container;

## Overview

- Injects objects of dependency classes through constructor or method by using built-in IoC container;

## Built-in IoC Container

- It does not have as many features as other third party IoC containers;
- If you want more features such as auto-registration, scanning, interceptors, or decorators then you may replace built-in IoC container with a third party container;
- The built-in container is represented by `IServiceProvider` implementation that supports constructor injection by default;
- The types (classes) managed by built-in IoC container is called **services**;

## Types of services

- There are basically two types of services in ASP.NET Core:

### Framework Services

- Services which are a part of ASP.NET Core framework such as IApplicationBuilder, IHostingEnvironment, ILoggerFactory etc;

### Application Services

- The services (custom types or classes) which you as a programmer create for your application;

## Registering Application Service

- Consider the following example of simple ILog interface and its implementation class;
- We will see how to register it with built-in IoC container and use it in our application:

```c#
public interface ILog
{
    void info(string str);
}

class MyConsoleLogger : ILog
{
    public void info(string str)
    {
        Console.WriteLine(str);
    }
}
```

- ASP.NET Core allows us to register our application services with IoC container, in the `ConfigureServices` method of the Startup class;
- The `ConfigureServices` method includes a parameter of `IServiceCollection` type which is used to register application services;
- For example:

```c#
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.Add(new ServiceDescriptor(typeof(ILog), new MyConsoleLogger()));
    }

    // other code removed for clarity..
}
```

- In the example, the `Add()` method of `IServiceCollection` instance is used to register a service with an IoC container;
- The `ServiceDescriptor` is used to specify a service type and its instance;
- We specifie `ILog` as service type and `MyConsoleLogger` as its instance;
- This will register `ILog` service as a singleton by default;
- Now, an IoC container will create a singleton object of `MyConsoleLogger` class and inject it in the constructor of classes wherever we include `ILog` as a constructor or method parameter throughout the application;

## Understanding Service Lifetime

- The built-in IoC Container will automatically dispose a service instance based on the specified lifetime;

### Types of lifetimes

- Singleton:
  - IoC container will create and share a single instance of a service throughout the application's lifetime;
- Transient:
  - The IoC container will create a new instance of the specified service type every time you ask for it;
- Scoped:
  - IoC container will create an instance of the specified service type once per request and will be shared in a single request;

### Registering a Service with Lifetime

- Example:

```c#
public void ConfigureServices(IServiceCollection services)
{
    services.Add(new ServiceDescriptor(typeof(ILog), new MyConsoleLogger()));    // singleton

    services.Add(new ServiceDescriptor(typeof(ILog), typeof(MyConsoleLogger), ServiceLifetime.Transient)); // Transient

    services.Add(new ServiceDescriptor(typeof(ILog), typeof(MyConsoleLogger), ServiceLifetime.Scoped));    // Scoped
}
```

## Extension Methods for Registration

- ASP.NET Core framework includes extension methods for each types of lifetime;

### Types of Extension Methods

- `AddSingleton()` -> for singleton;
- `AddTransient()` -> for transient;
- `AddScoped()` -> scoped lifetime;
- Example:

```c#
public void ConfigureServices(IServiceCollection services)
{
    services.AddSingleton<ILog, MyConsoleLogger>();
    services.AddSingleton(typeof(ILog), typeof(MyConsoleLogger));

    services.AddTransient<ILog, MyConsoleLogger>();
    services.AddTransient(typeof(ILog), typeof(MyConsoleLogger));

    services.AddScoped<ILog, MyConsoleLogger>();
    services.AddScoped(typeof(ILog), typeof(MyConsoleLogger));
}
```

## Constructor Injection

- Once we register a service, the IoC container automatically performs constructor injection if a service type is included as a parameter in a constructor;
- For example:

```c#
public class HomeController : Controller
{
    ILog _log;

    public HomeController(ILog log)
    {
        _log = log;
    }
    public IActionResult Index()
    {
        _log.info("Executing /home/index");

        return View();
    }
}
```

- Here, an IoC container will create and dispose an instance of ILog based on the registered lifetime automatically, as an instance of `MyConsoleLogger` is passed automatically to `HomeController`;

## Action Method Injection

- When we need dependy services in a single action method, use `FromServices` attribute with the service type parameter in the method;
- Example:

```c#
using Microsoft.AspNetCore.Mvc;

public class HomeController : Controller
{
    public HomeController()
    {
    }

    public IActionResult Index([FromServices] ILog log)
    {
        log.info("Index method executing");

        return View();
    }
}
```

## Property Injection

- Built-in IoC container does not support property injection;
- For this, use a third party IoC Container;

## Get Services Manually

- If you want, We can access dependent services configured with built-in IoC container manually using `RequestServices` property of `HttpContext` as shown below;
- Example:

```c#
public class HomeController : Controller
{
    public HomeController()
    {
    }
    public IActionResult Index()
    {
        var services = this.HttpContext.RequestServices;
        var log = (ILog)services.GetService(typeof(ILog));

        log.info("Index method executing");

        return View();
    }
}
```

- It is recommended to use constructor injection instead of getting it using `RequestServices`.;

## Links

- <https://www.tutorialsteacher.com/core/dependency-injection-in-aspnet-core> ;
