# Built-in IoC Container

## Overview

- ASP.NET Core is designed from scratch to support Dependency Injection;
- ASP.NET Core injects objects of dependency classes through constructor or method by using built-in IoC container;

## Built-in IoC Container

- ASP.NET Core framework includes built-in IoC container for automatic dependency injection;
- The built-in IoC container is a simple yet effective container;
- The followings are important interfaces and classes for built-in IoC container:

### Interfaces

- IServiceProvider;
- IServiceCollection;

### Classes

- ServiceProvider;
- ServiceCollection;
- ServiceDescription;
- ServiceCollectionServiceExtensions;
- ServiceCollectionContainerBuilderExtensions;

![IoC Container](https://github.com/JoaoGuimaraes22/2020-Todo/blob/master/Images/Backend/Initial%20Learning/Learn%20a%20language/Functional%20Language/C%23/2.1.6.1.builtin-ioc-min.png)

## IServiceCollection

- We can register application services with built-in IoC container in the Configure method of Startup class by using IServiceCollection;
- IServiceCollection interface is an empty interface. It just inherits `IList<servicedescriptor>`;
- The ServiceCollection class implements IServiceCollection interface;
- When you add in the `IServiceCollection` type instance, it actually creates an instance of ServiceDescriptor and adds it to the list.

## ServiceCollectionServiceExtensions

- The `ServiceCollectionServiceExtensions` class includes extension methods related to service registrations which can be used to add services with lifetime;
- AddSingleton, AddTransient, AddScoped extension methods are defined in this class.

## Using IApplicationBuilder

- We get the services in the Configure method using IApplicationBuilder's `ApplicationServices` property;
- For example:

```c#
public void Configure(IServiceProvider pro, IApplicationBuilder app, IHostingEnvironment env)
{
    var services = app.ApplicationServices;
    var logger = services.GetService<ILog>() }

    //other code removed for clarity
}
```

## Using HttpContext

- For example:

```c#
var services = HttpContext.RequestServices;
var log = (ILog)services.GetService(typeof(ILog));
```

## Using IServiceCollection

- For example:

```c#
public void ConfigureServices(IServiceCollection services)
{
    var serviceProvider = services.BuildServiceProvider();

}
```

## Links

- <https://www.tutorialsteacher.com/core/internals-of-builtin-ioc-container-in-aspnet-core> ;
