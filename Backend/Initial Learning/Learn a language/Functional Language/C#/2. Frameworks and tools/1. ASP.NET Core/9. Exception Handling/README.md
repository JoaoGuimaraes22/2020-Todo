# Exception Handling

## Overview

- ASP.NET Core includes a middleware that makes exception handling easy;
- By default, ASP.NET Core returns a simple status code for any exception that occurs in an application;
- Consider the following example of Configure method which throws an error:

```c#
public class Startup
{
    public void Configure(IApplicationBuilder app, IHostingEnvironment env)
    {
        app.Run(context => { throw new Exception("error"); });
    }
}
```

- The above code will display the page with **HTTP ERROR 500**.

## Install Microsoft.AspNetCore.Diagnostics Package

- To handle exceptions and display user friendly messages, we need to install `Microsoft.AspNetCore.Diagnostics` NuGet package and add middleware in the `Configure()` method;
- If you are using Visual Studio templates to create ASP.NET Core application then this package might be already installed;
- If not then you can add `Microsoft.AspNetCore.Diagnostics` package via NuGet manager;
- `The Microsoft.AspNetCore.Diagnostics` package includes following extension methods to handle exceptions in different scenario:
  - UseDeveloperExceptionPage;
  - UseExceptionHandler.

## UseDeveloperExceptionPage

- The `UseDeveloperExceptionPage` extension method adds middleware into the request pipeline which displays developer friendly exception detail page;
- This helps developers in tracing errors that occur during development phase;
- As this middleware displays sensitive information, it is advisable to add it only in development environment;
- For example:

```c#
public class Startup
{
    public void Configure(IApplicationBuilder app, IHostingEnvironment env)
    {
        if (env.IsDevelopment() || env.IsStaging())
        {
            app.UseDeveloperExceptionPage();
        }

        app.Run(context => { throw new Exception("error"); });
    }
}
```

- The developer exception page includes 4 tabs: Stack, Query, Cookies, and Headers;
- Stack tab displays information of stack trace, which indicates where exactly an error occurred;
- Query tab displays information about query string;
- Cookies tab displays information about cookies set by the request and Headers tab displays information about headers.

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-exception-handling> ;
