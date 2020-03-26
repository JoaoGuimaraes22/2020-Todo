# Project Structure

## Here you will learn about

- Project Structure;
  - wwwroot;
  - Program.cs;
  - Startup.cs;

## Overview

- The following is a default project structure when you create an empty ASP.NET Core application in Visual Studio:
  ![Defaul Structure](https://github.com/JoaoGuimaraes22/2020-Todo/blob/master/Images/Backend/Initial%20Learning/Learn%20a%20language/Functional%20Language/C%23/2.1.4.core-app-project-structure-min.png)

## Solution Explorer

- The above solution explorer displays project solution;
- We can change it to folder view by -> clicking **Solution and Folders** icon -> and selecting **Folder View** option
- This displays the solution explorer with all project folders and files as shown below;

## .csproj

- The .csproj is used tp file to manage projects;
- The .csproj file includes settings related to targeted .NET Frameworks, project folders, NuGet package references etc;

## Dependencies

- The Dependencies in the ASP.NET Core 2.0 project contain all the installed server-side NuGet packages as well as client-side frameworks such as jQuery, AngularJS, Bootstrap with Bower;
- You can see your dependencies in the **dependencies** node;
- This includes the NuGet Packages and the Bower folder;

## Properties

- The Properties node includes launchSettings.json file which includes Visual Studio profiles of debug settings;
- We can also edit settings from the debug tab of project properties;
- Right click on the **project** -> select **Properties** -> click **Debug** tab;
- In the debug tab, select a profile which you want to edit as shown above;
- You may change environment variables, url etc;

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-application-project-structure> ;
