# Configure the Default File to be Served on the Root Request

## Overview

- The `app.UseDefaultFiles()` middleware serves the following files on the root request:
  - Default.html
  - Default.htm
  - Index.html
  - Index.htm

## Changing default root access page

- Suppose, you want to set home.html as a default page which should be displayed on the root access;
- To do that, specify `DefaultFilesOptions` in the `UseDefaultFiles` method as shown below:

```c#
public class Startup
{
    public void Configure(IApplicationBuilder app, IHostingEnvironment env)
    {
        DefaultFilesOptions options = new DefaultFilesOptions();
        options.DefaultFileNames.Clear();
        options.DefaultFileNames.Add("home.html");
        app.UseDefaultFiles(options);

        app.UseStaticFiles();

        app.Run(async (context) =>
        {
            await context.Response.WriteAsync("Hello World");
        });
    }
}
```

- This will display home.html from wwwroot folder on the root request http://localhost:<port>.

## Links

- <https://www.tutorialsteacher.com/core/how-to-change-the-name-of-the-default-file-to-be-served-on-root-request> ;
