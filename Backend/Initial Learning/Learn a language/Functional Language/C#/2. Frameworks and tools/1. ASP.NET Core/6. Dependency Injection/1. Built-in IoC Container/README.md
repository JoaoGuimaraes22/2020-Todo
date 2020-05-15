# Built-in IoC Container

## Overview

- ASP.NET Core is designed from scratch to support Dependency Injection;
- ASP.NET Core injects objects of dependency classes through constructor or method by using built-in IoC container;

## Built-in IoC Container

- ASP.NET Core framework contains simple out-of-the-box IoC container;
- If you want more features such as auto-registration, scanning, interceptors, or decorators then you may replace built-in IoC container with a third party container;

### Services in ASP.NET Core

- Framework Services:
  - Services which are a part of ASP.NET Core framework such as IApplicationBuilder, IHostingEnvironment, ILoggerFactory, etc;
- Application Services:
  - The services (custom types or classes) which you create for your application;

## Registering Application Service

- In order to let the IoC container automatically inject our application services, we first need to register them with IoC container;
- Consider the following example of simple ILog interface and its implementation class:

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
- Example (Register Service):

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

- Here, the `Add()` method of `IServiceCollection` instance is used to register a service with an IoC container;
- The `ServiceDescriptor` is used to specify a service type and its instance;
- `ILog`'s specified as service type and `MyConsoleLogger` as its instance;
- This will register `ILog` service as a singleton;
- Now, an IoC container will create a singleton object of `MyConsoleLogger` class and inject it in the constructor of classes wherever we include ILog as a constructor or method parameter;
- As such, we can register our custom application services with an IoC container, althought there are other methods;

## Understanding Service Lifetime

- Built-in IoC container manages the lifetime of a registered service type, automatically disposeing a service instance based on it's specified lifetime;

### Different Types of Service Lifteimes

- **Singleton:**
  - IoC container will create and share a single instance of a service throughout the application's lifetime;
- **Transient:**
  - The IoC container will create a new instance of the specified service type every time you ask for it;
- **Scoped:**
  - IoC container will create an instance of the specified service type once per request and will be shared in a single request;
- Example (Registering different types of services):

```c#
public void ConfigureServices(IServiceCollection services)
{
    services.Add(new ServiceDescriptor(typeof(ILog), new MyConsoleLogger()));    // singleton

    services.Add(new ServiceDescriptor(typeof(ILog), typeof(MyConsoleLogger), ServiceLifetime.Transient)); // Transient

    services.Add(new ServiceDescriptor(typeof(ILog), typeof(MyConsoleLogger), ServiceLifetime.Scoped));    // Scoped
}
```

## Extension Methods for Registration

- There are extension methods for each types of lifetime: AddSingleton(), AddTransient() and AddScoped() methods for singleton, transient and scoped lifetime respectively;
- Example (Extension Methods):

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

## Contructor Injection

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

- In the above example, an IoC container will automatically pass an instance of MyConsoleLogger to the constructor of `HomeController`;
- An IoC container will create and dispose an instance of `ILog` based on the registered lifetime;

## Action Method injection

- Sometimes we may only need dependency service type in a single action method;
- For this, use `[FromServices]` attribute with the service type parameter in the method;

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
- You will have to use third party IoC container;

## Get Services Manually

- It isn't required to include dependency services in the constructor;
- We can access dependent services configured with built-in IoC container manually using `RequestServices` property of `HttpContext` as shown below;

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

- It is recommended to use constructor injection instead of getting it using `RequestServices`;

## Links

- <https://www.tutorialsteacher.com/core/internals-of-builtin-ioc-container-in-aspnet-core> ;
