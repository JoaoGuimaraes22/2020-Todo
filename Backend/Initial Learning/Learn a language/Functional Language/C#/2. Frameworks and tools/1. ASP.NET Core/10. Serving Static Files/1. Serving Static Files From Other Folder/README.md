# Serve static files from different folder than wwwroot folder in ASP.NET Core

## Overview

- You can configure middleware to serve static files from other folders along with default web root folder wwwroot;
- For example, we will serve a file admin.html from the an example "admin" folder (outside of the wwwroot folder) and also another file test.html from the wwwroot folder;
- Now, configure the StaticFiles middleware in the Configure() method of Startup class as shown below:

```c#
public class Startup
{
    // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
    public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
    {
        app.UseStaticFiles();

        app.UseStaticFiles(new StaticFileOptions() {
                FileProvider =  new PhysicalFileProvider(Path.Combine(Directory.GetCurrentDirectory(), "Content")),
                RequestPath = new PathString("/Admin")
        });

        app.Run(async (context) =>
        {
            await context.Response.WriteAsync("Hello World!");
        });
    }
}
```

- As you can see, `app.UseStaticFiles()` enables default web root folder wwwroot to serve the static files;
- For example:

```c#
app.UseStaticFiles(new StaticFileOptions() {
    FileProvider =  new PhysicalFileProvider(Path.Combine(Directory.GetCurrentDirectory(), "admin")),
    RequestPath = new PathString("/admin")
});
```

- The above code configures Content admin folder to serve static files on the request path /admin;
- So now, we will be able to execute HTTP request http://localhost:1234/admin/admin.html to display static admin.html page.

## Links

- <https://www.tutorialsteacher.com/core/how-to-serve-static-files-from-another-folder-other-than-wwwroot> ;
