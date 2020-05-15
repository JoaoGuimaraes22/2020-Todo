# Middleware

## Here you will learn about

1. Middleware:
   1. Add Custom Middleware;
   2. Configure Default File;

## Overview

- A middleware is nothing but a component (class) which is executed on every request in ASP.NET Core application;
- Middleware is similar to HttpHandlers and HttpModules where both needs to be configured and executed in each request;
- Middleware can be either framework provided middleware, added via NuGet or your own custom middleware;
- The order of middleware execution in set in the request pipeline;
- Each middleware adds or modifies http request and optionally passes control to the next middleware component;
- The following figure illustrates the execution of middleware components:
  [Middleware Image]()

## Links

- <https://www.tutorialsteacher.com/core/aspnet-core-middleware> ;
