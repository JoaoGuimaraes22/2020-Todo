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

## UseExceptionHandler

- In an MVC Core application, we might want some other controller to handle all exceptions and display custom user friendly error messages;
- The `UseExceptionHandler` extension method allows us to configure custom error handling route;
- This is useful when an application runs under production environment;
- For example:

```c#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{

    if (env.IsDevelopment() || env.IsStaging())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Home/Error");
    }

    //code removed for clarity
}
```

- In the above example, the `UseExceptionHandler("/Home/Error")` sets the error handler path;
- If an error occurred in the MVC application then it will redirect the request to `/home/error`, which will execute the Error action method of `HomeController`;
- Create a simple Error action method in `HomeController` class as shown below:

```c#
public class HomeController : Controller
{
    public HomeController()
    {
    }

    public IActionResult Error()
    {
        return View();
    }

    // other code removed for the clarity

}
```

- The following is the content of Error.cshtml:

```html
@{ ViewData["Title"] = "Error"; }

<h1 class="text-danger">Error.</h1>
<h2 class="text-danger">An error occurred while processing your request.</h2>

<h3>Development Mode</h3>
<p>
  Swapping to <strong>Development</strong> environment will display more
  detailed information about the error that occurred.
</p>
<p>
  <strong
    >Development environment should not be enabled in deployed
    applications</strong
  >, as it can result in sensitive information from exceptions being displayed
  to end users. For local debugging, development environment can be enabled by
  setting the <strong>ASPNETCORE_ENVIRONMENT</strong> environment variable to
  <strong>Development</strong>, and restarting the application.
</p>
```

- Visual Studio automatically creates Error.cshtml under Home folder when you create ASP.NET Core project with MVC template.

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-exception-handling> ;
