# Startup Class

## Overview

- ASP.NET Core application must include Startup class;
- Excuted first;
- The `Startup` class can be configured using `UseStartup<T>()` method at the time of configuring the host in the `Main()` method of `Program` class as shown below:

```c#
public class Program
{
    public static void Main(string[] args)
    {
        BuildWebHost(args).Run();
    }

    public static IWebHost BuildWebHost(string[] args)
    {
        WebHost.CreateDefaultBuilder(args)
            .UseStartup<Startup>()
            .Build();
    }
}
```

- We can give any name to the `Startup` class, just specify it as the generic parameter in the `UseStartup<T>()` method;

## Startup

- Startup class includes two public methods: **ConfigureServices** and **Configure**;
- The Startup class must include a Configure method and can optionally include ConfigureService method;

## ConfigureServices()

- The Dependency Injection pattern is used heavely;
- It includes built-in IoC container to provide dependent objects using constructors;
- The ConfigureServices method is a place where you can register your dependent classes with the built-in IoC container;
- ASP.NET Core refers dependent class as a Service;
- ConfigureServices method includes IServiceCollection parameter to register services to the IoC container;

## Configure

- It's a place where you can configure application request pipeline for your application using IApplicationBuilder instance that is provided by the built-in IoC container;
- Here, middleware components to define a request pipeline are included which will be executed on every request;
- Example:

```c#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.Run(async (context) =>
    {
        await context.Response.WriteAsync("Hello World!");
    });
}
```

- Here, there are three paremeters IApplicationBuilder, IHostingEnvironment, and ILoggerFactory;
- These services are framework services injected by built-in IoC container;
- At run time, the ConfigureServices method is called before the Configure method;

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-startup> ;
