# Middleware

## Here you will learn about

1. Middleware:
   1. Add Custom Middleware;
   2. Configure Default File;

## Overview

- A middleware is a component (class) which is executed on every request in an ASP.NET Core application;
- Middleware is similar to HttpHandlers and HttpModules where both need to be configured and executed in each request;
- Middleware can be either framework provided, added via NuGet or your own custom middleware;
- The order of middleware execution in set in the request pipeline;
- Each middleware adds or modifies http request and optionally passes control to the next middleware component;

- The following figure illustrates the execution of middleware components:
  ![Middleware ASP.NET Core](https://github.com/JoaoGuimaraes22/2020-Todo/blob/master/Images/Backend/Initial%20Learning/Learn%20a%20language/Functional%20Language/C%23/2.1.7.middleware-1-min.png)

- Middlewares build the request pipeline, as shown:
  ![Middleware Request Processing](https://github.com/JoaoGuimaraes22/2020-Todo/blob/master/Images/Backend/Initial%20Learning/Learn%20a%20language/Functional%20Language/C%23/2.1.7.request-processing-min.png)

## Configure Middleware

- We configure middleware in the `Configure` method of the Startup class using the `IApplicationBuilder` instance;
- The following example adds a single middleware using Run method which returns a string "Hello World!" on each request:
- Here, `Run()` is an extension method on IApplicationBuilder instance which adds a terminal middleware to the application's request pipeline, which returns a response with a string "Hello World!" for each request.

```c#
public class Startup
{
    public Startup()
    {
    }
    public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
    {
        //configure middleware using IApplicationBuilder here..

        app.Run(async (context) =>
        {
            await context.Response.WriteAsync("Hello World!");

        });

        // other code removed for clarity..
    }
}
```

## Understanding the "Run" Method

- We used the Run extension method to add middleware;
- The following is the signature of the Run method:

```c#
public static void Run(this IApplicationBuilder app, RequestDelegate handler)
```

- The Run method is an extension method on `IApplicationBuilder` and accepts a parameter of `RequestDelegate`;
- The `RequestDelegate` is a delegate method which handles the request;
- The following is a RequestDelegate signature:

```c#
public delegate Task RequestDelegate(HttpContext context);
```

- Here, the `Run` method accepts a method as a parameter whose signature should match with `RequestDelegate`;
- Therefore, the method should accept the `HttpContext` parameter and return `Task`;
- So, you can either specify a lambda expression or specify a function in the Run method;
- The lambda expression specified in the Run method above is similar to the one in the example shown below:

```c#
public class Startup
{
    public Startup()
    {
    }

    public void Configure(IApplicationBuilder app, IHostingEnvironment env)
    {
         app.Run(MyMiddleware);
    }

    private Task MyMiddleware(HttpContext context)
    {
        return context.Response.WriteAsync("Hello World! ");
    }
}
```

- The above `MyMiddleware` function is not asynchronous, and so will block the thread untill the time it completes the execution;
- So, make it asynchronous by using async and await to improve performance and scalability:

```c#
// other code removed for clarity

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
     app.Run(MyMiddleware);
}

private async Task MyMiddleware(HttpContext context)
{
    await context.Response.WriteAsync("Hello World! ");
}
```

- The above code snippet is same as the one below:

```c#
app.Run(async context => await context.Response.WriteAsync("Hello World!") );

//or

app.Run(async (context) =>
{
    await context.Response.WriteAsync("Hello World!");
});
```

## Configure Multiple Middleware

- Most of the time there will be multiple middleware components in an ASP.NET Core application which will be executed sequentially;
- The Run method adds a terminal middleware so it cannot call next middleware as it would be the last middleware in a sequence;
- The following will always execute the first Run method and will never reach the second Run method:

```c#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    app.Run(async (context) =>
    {
        await context.Response.WriteAsync("Hello World From 1st Middleware");
    });

    // the following will never be executed
    app.Run(async (context) =>
    {
        await context.Response.WriteAsync("Hello World From 2nd Middleware");
    });
}
```

- To configure multiple middleware, we use the `Use()` extension method;
- It is similar to the `Run()` method, except that it includes the next parameter to invoke the next middleware in the sequence;
- Consider the following example:

```c#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    app.Use(async (context, next) =>
    {
        await context.Response.WriteAsync("Hello World From 1st Middleware!");

        await next();
    });

    app.Run(async (context) =>
    {
        await context.Response.WriteAsync("Hello World From 2nd Middleware");
    });
}
```

- The above example displays `Hello World From 1st Middleware!Hello World From 2nd Middleware!` in the browser.
- Thus, we can use the `Use()` method to configure multiple middlewares in the order we like.

## Add Built-in Middleware Via NuGet

- We can add server side features we need in our application by installing different plug-ins via NuGet;
- There are many middleware plug-ins available which can be used in our application;
- The followings are some built-in middleware:
  - **Authentication** - Adds authentication support;
  - **CORS** - Configures Cross-Origin Resource Sharing;
  - **Routing** - Adds routing capabilities for MVC or web form;
  - **Session** - Adds support for user session;
  - **StaticFiles** - Adds support for serving static files and directory browsing;
  - **Diagnostics** - Adds support for reporting and handling exceptions and errors.

## Diagnostics Middleware

- Diagnostics middleware is used for reporting and handling exceptions and errors in ASP.NET Core, and diagnosing Entity Framework Core migrations errors;
- Open project.json and add Microsoft.AspNetCore.Diagnostics dependency if it is not added;
- Wait for some time until the packages are restored;
- This package includes following middleware and extension methods for it:
  - **DeveloperExceptionPageMiddleware** - UseDeveloperExceptionPage() -> Captures synchronous and asynchronous exceptions from the pipeline and generates HTML error responses;
  - **ExceptionHandlerMiddleware** - UseExceptionHandler() -> Catch exceptions, log them and re-execute in an alternate pipeline;
  - **StatusCodePagesMiddleware** - UseStatusCodePages() -> Check for responses with status codes between 400 and 599;
  - **WelcomePageMiddleware** - UseWelcomePage() -> Display Welcome page for the root path;
- We can call respective Use\* extension methods to use the above middleware in the configure method of Startup class;
- For example:

```c#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    app.UseWelcomePage();
    //other code removed for clarity
}
```

- The above example will a welcome page for each request;
- This way we can use different Use\* extension methods to include different middleware;

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-middleware> ;
