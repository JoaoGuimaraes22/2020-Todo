# wwwroot

## Overview

- The wwwroot folder in the ASP.NET Core project is treated as a web root folder;
- Static files can be stored in any folder under the web root and accessed with a relative path to that root;
- Only files in the wwwroot folder can be served over an http request by default;

## Structure

- Generally, there should be separate folders for the different types of static files such as JavaScript, CSS, Images, library scripts etc;
  ![Structure wwwroot](https://github.com/JoaoGuimaraes22/2020-Todo/blob/master/Images/Backend/Initial%20Learning/Learn%20a%20language/Functional%20Language/C%23/2.1.4.1.wwwroot-min.png)

## Access Static Files

- You can access static files with base URL and file name;
- For example, we can access above site.css file in the css folder by `http://localhost:<port>/css/app.css`;
- You will need a middleware for serving static files in Startup.cs in the Configure method;

## Rename wwwroot folder

- When you change the wwwroot folder name, you need to call UseWebRoot() method to configure Content folder as a web root folder in the Main() method of a Program class;
- Example:

```c#
public class Program
{
    public static void Main(string[] args)
    {
        var host = new WebHostBuilder()
            .UseKestrel()
            .UseContentRoot(Directory.GetCurrentDirectory())
            .UseWebRoot("Content")
            .UseIISIntegration()
            .UseStartup<MyStartup>()
            .Build();

        host.Run();
    }
```

- Thus, you can rename the default web root folder wwwroot as per your choice;

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-wwwroot> ;
