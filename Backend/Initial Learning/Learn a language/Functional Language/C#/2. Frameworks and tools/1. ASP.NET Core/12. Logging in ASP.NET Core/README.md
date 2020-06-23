# Logging in ASP.NET Core

## Overview

- ASP.NET Core uses the same logging mechanism as .NET Core logging;
- The logging API in `Microsoft.Extensions.Logging` namespace works with one or more built-in or third party logging providers;
- So, in an ASP.NET Core MVC application, we will also have to install the NuGet package `Microsoft.Extensions.Logging` and one or more logging providers of our choice;

## Using Visual Studio

- Create an ASP.NET Core MVC application in Visual Studio 2017 (or later);
- When you create the ASP.NET Core MVC web application in Visual Studio 2017 (or later), it automatically includes the NuGet package for `Microsoft.Extensions.Logging` and the following logging providers under the `Microsoft.AspNetCore.App` NuGet package:
  - Microsoft.Extensions.Logging.Console;
  - Microsoft.Extensions.Logging.Debug;
  - Microsoft.Extensions.Logging.EventSource;
  - Microsoft.Extensions.Logging.TraceSource.

## Add Logging Providers

- In the ASP.NET Core MVC application, the call to `the WebHost.CreateDefaultBuilder(args)` method in the Program.cs internally adds the Console, Debug, and EventSource logging providers;
- For example:

```c#
public class Program
{
    public static void Main(string[] args)
    {
        CreateWebHostBuilder(args).Build().Run();
    }

    public static IWebHostBuilder CreateWebHostBuilder(string[] args) =>
        WebHost.CreateDefaultBuilder(args)
               .UseStartup<Startup>();
}
```

- Look at the source code of the `WebHost.CreateDefaultBuilder()` method on GitHub and you will find the following code:

```c#
.ConfigureLogging((hostingContext, logging) =>
    {
        logging.AddConfiguration(hostingContext.Configuration.GetSection("Logging"));
        logging.AddConsole();
        logging.AddDebug();
        logging.AddEventSourceLogger();
    }).
```

- Ff you want to use these providers, there's no need to add them manually;
- If you want to use other providers or any default provider, then you need to remove all the existing providers and add the provider of your choice;
- To configure logging providers, call the `ConfigureLogging()` extension method of `IWebHostBuilder`, as shown below:

```c#
public static IWebHostBuilder CreateWebHostBuilder(string[] args) =>
    WebHost.CreateDefaultBuilder(args)
    .ConfigureLogging(logBuilder =>
    {
        logBuilder.ClearProviders(); // removes all providers from LoggerFactory
        logBuilder.AddConsole();
        logBuilder.AddTraceSource("Information, ActivityTracing"); // Add Trace listener provider
    })
    .UseStartup<Startup>();
```

- In the above example, the `ConfigureLogging()` method takes action to delegate `Action<ILogBuilder>` to configure logging providers;
- To add logging providers of your choice, remove all the default providers using `ClearProviers()` and then call the extension method of a provider to add it, such as `AddTraceSource()` which will add the trace listener provider, and the `AddConsole()` method which will add the Console logging provider.

- You can also configure the logging provider using `ILoggerFactory` in the `Configure()` method of the `Startup` class.

## Storing Logs in a Text File

- To store logs in a file, install the NuGet package `Serilog.Extensions.Logging.File`;
- Serillog includes an extension method for `ILoggerFactory` but not for `ILogBuilder` (in v 1.1.0);
- So, go to the `Startup.cs` file and add the `ILoggerFactory` parameter in the `Configure()` method;
- Then, call the `AddFile()` extension method to add Serillog file provider;
- ASP.NET Core dependency injection will automatically pass an instance of the `LoggerFactory` for this parameter;
- For example, in Startup.cs:

```c#
public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
{
    // other code remove for clarity
    loggerFactory.AddFile("Logs/mylog-{Date}.txt");
}
```

- This will store all the logs in the `mylog-<date>.txt` file, under the Logs folder in your application.

## Create Logs in the Controller

- We can use `ILogger` or `ILoggerFactory` anywhere in an application using ASP.NET Core DI (Dependency Injection);
- Consider the following example of HomeController:

```c#
namespace AspDotNetCoreMvcApp.Controllers
{
    public class HomeController : Controller
    {
        private readonly ILogger _logger;

        public HomeController(ILogger<HomeController> logger){
            _logger = logger;
        }

        public IActionResult Index()
        {
            _logger.LogInformation("Log message in the Index() method");

            return View();
        }

        public IActionResult About()
        {
            _logger.LogInformation("Log message in the About() method");

            return View();
        }
    }
}
```

- Here, the `ILogger<HomeController>` parameter is included in the constructor;
- ASP.NET Core DI will pass the `ILogger` instance, which can be used to log in the `Index()` and `About()` action methods;

- Passing HomeController as generic type for the `ILogger<HomeController>`, will be used as a category;
- For example, specifying `ILogger<HomeController>` will display a fully qualified name `AspDotNetCoreMvcApp.Controllers.HomeController` in the logs;
- For example:

```bash
info: AspDoteNetCoreMvcApp.Controllers.HomeController[0]
       Log message in the Index() method
```

- Here, we logged information using the `LogInformation()` method, so it starts with "info:" followed by the fully qualified name of the class where a log is created: `AspDoteNetCoreMvcApp.Controllers.HomeController[0]`;
- [0] is the event id;
- You can specify this event id to identify a record, e.g. Id, page number or other important information which uniquely identifies a log;
- We didn't specify any event id, so it will be 0;
- The next line is an actual log message: "Log message in the Index() method";

- The same can be achieved by passing `ILoggerFactory` in the constructor;
- For example:

```c#
public class HomeController : Controller
{
    private readonly ILogger _logger;

    public HomeController(ILoggerFactory logFactory)
    {
        _logger = logFactory.CreateLogger<HomeController>();
    }

    public IActionResult Index()
    {
        _logger.LogInformation("Log message in the Index() method");

        return View();
    }

    public IActionResult About()
    {
        _logger.LogInformation("Log message in the About() method");

        return View();
    }
}
```

- Running the above application from the command prompt by navigating to `/<app root folder>/bin/debug/netcoreapp2.1/`, running the `dotnet <app name>.dll` command and then opening <http://localhost:5000> in the browser, will display the same logs on the Console as below:

```bash
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/
info: Microsoft.AspNetCore.Mvc.Internal.ControllerActionInvoker[1]
      Route matched with {action = "Index", controller = "Home"}. Executing acti
on AspDoteNetCoreMvcApp.Controllers.HomeController.Index (AspDotNetCoreMvcApp)
info: Microsoft.AspNetCore.Mvc.Internal.ControllerActionInvoker[1]
      Executing action method AspDoteNetCoreMvcApp.Controllers.HomeController.In
dex (AspDotNetCoreMvcApp) - Validation state: Valid
info: AspDoteNetCoreMvcApp.Controllers.HomeController[0]
      Log message in the Index() method
info: Microsoft.AspNetCore.Mvc.Internal.ControllerActionInvoker[2]
      Executed action method AspDoteNetCoreMvcApp.Controllers.HomeController.Ind
ex (AspDotNetCoreMvcApp), returned result Microsoft.AspNetCore.Mvc.ViewResult in
 0.8505ms.
info: Microsoft.AspNetCore.Mvc.ViewFeatures.ViewResultExecutor[1]
      Executing ViewResult, running view Index.
info: Microsoft.AspNetCore.Mvc.ViewFeatures.ViewResultExecutor[4]
      Executed ViewResult - view Index executed in 231.2839ms.
info: Microsoft.AspNetCore.Mvc.Internal.ControllerActionInvoker[2]
      Executed action AspDoteNetCoreMvcApp.Controllers.HomeController.Index (Asp
DotNetCoreMvcApp) in 288.6931ms
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 946.274ms 200 text/html; charset=utf-8
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/images/banner1.svg
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/images/banner2.svg
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 5.6471ms 404
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 6.5811ms 404
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/css/site.min.css
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 0.2811ms 404
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/js/site.min.js
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/images/banner3.svg
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 0.178ms 404
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 0.2342ms 404
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/css/site.min.css
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 0.1173ms 404
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/js/site.min.js
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 0.2539ms 404
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[1]
      Request starting HTTP/1.1 GET http://localhost:5000/favicon.ico
info: Microsoft.AspNetCore.Hosting.Internal.WebHost[2]
      Request finished in 0.3253ms 404
```

- Visit <https://docs.microsoft.com/en-us/aspnet/core/fundamentals/logging/?view=aspnetcore-3.1> for more detailed information.

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-logging> ;
