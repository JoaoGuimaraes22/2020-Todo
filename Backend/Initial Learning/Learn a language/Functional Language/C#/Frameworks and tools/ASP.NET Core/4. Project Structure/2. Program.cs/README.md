# Program.cs

## Overview

- ASP.NET Core web application is actually a console project which starts executing from the entry point `public static void Main()` in Program class where we can create a host for the web application;

## Setup Host in ASP.NET Core 1.x

- The following is a typical Program.cs in ASP.NET Core 1.x:

```c#
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Hosting;

namespace MyFirstCoreApp
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();

            host.Run();
        }
    }
}
```

- Requires a host to be executed;
- A host must implement IWebHost interface;
- Example:

```c#
var host = new WebHostBuilder()
```

### .UseKestrel()

- It's an extension method which specifies Kestrel as an internal web server;
- The Kestrel is a web server designed to be used behind a proxy;

### .UseContentRoot(Directory.GetCurrentDirectory())

- Specifies the current directory as a root directory which will be src folder default;
- The content root directory determines where the content files are located such as MVC view files, CSS, images etc;

### .UseIISIntegration()

- Specifies the IIS as the external web server or the reverse proxy server;

### .UseStartup`<Startup>`()

- Specifies the Startup class to be used by the web host;
- Here, you can configure the request pipeline (middleware);
- Finnaly, the `Build()` method returns an instance of IWebHost using the configuration specified above;

### host.Run()

- Starts the web application and blocks the calling thread till the host is shutdown,
- Thus, ASP.NET Core application starts from the `Main()` method of the Program class where you can build the hosting environment and start the web application;

## Setup Host in ASP.NET Core 2.x

- The following is the Program class in ASP.NET Core 2.x:

```c#
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Hosting;

namespace MyFirstCoreApp
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args) =>
            WebHost.CreateDefaultBuilder(args)
                .UseStartup<Startup>()
                .Build();
    }
}
```

- As you can see above, `the Main()` method calls method expression `BuildWebHost()` to build web host with pre-configured defaults;
- The `BuildWebHost` expression can also be written as a method that returns `IWebHost` as shown below:

```c#
public static void Main(string[] args)
{
    BuildWebHost(args).Run();
}

public static IWebHost BuildWebHost(string[] args)
{
    return WebHost.CreateDefaultBuilder(args)
        .UseStartup<Startup>()
        .Build();
}
```

## Hosting Steps

- The `WebHost` is a static class which can be used for creating an instance of `IWebHost` and `IWebHostBuilder` with pre-configured defaults;
- The `CreateDefaultBuilder()` method creates a new instance of `WebHostBuilder` with pre-configured defaults;
- It configures Kestrel, IISIntegration and other configurations;
- The following is CreateDefaultBuilder() method from the source code on GitHub:

```c#
public static IWebHostBuilder CreateDefaultBuilder(string[] args)
{
    var builder = new WebHostBuilder()
        .UseKestrel()
        .UseContentRoot(Directory.GetCurrentDirectory())
        .ConfigureAppConfiguration((hostingContext, config) =>
        {
            var env = hostingContext.HostingEnvironment;

            config.AddJsonFile("appsettings.json", optional: true, reloadOnChange: true)
                    .AddJsonFile($"appsettings.{env.EnvironmentName}.json", optional: true, reloadOnChange: true);

            if (env.IsDevelopment())
            {
                var appAssembly = Assembly.Load(new AssemblyName(env.ApplicationName));
                if (appAssembly != null)
                {
                    config.AddUserSecrets(appAssembly, optional: true);
                }
            }

            config.AddEnvironmentVariables();

            if (args != null)
            {
                config.AddCommandLine(args);
            }
        })
        .ConfigureLogging((hostingContext, logging) =>
        {
            logging.AddConfiguration(hostingContext.Configuration.GetSection("Logging"));
            logging.AddConsole();
            logging.AddDebug();
        })
        .UseIISIntegration()
        .UseDefaultServiceProvider((context, options) =>
        {
            options.ValidateScopes = context.HostingEnvironment.IsDevelopment();
        });

    return builder;
}
```

- As you can see above, the `CreateDefaultBuilder` method creates an instance of `WebHostBuilder` and sets up Kestrel, content root directory, IIS integration which is same as ASP.NET Core 1.x `Main()` method;
- It also calls `ConfigureAppConfiguration()` to load configurations from appsettings.json files, environment variables and user secrets;
- The `ConfigureLogging()` method setup logging to console and debug window;

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-program;>
