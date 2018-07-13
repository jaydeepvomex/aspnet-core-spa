# Building ASP.NET Core to build Single-Page Applications

## Getting Started

### Installing the Templates for .NET cli

Create a new folder in C:\Project\aspnet-core-spa and install the templates

```bash
$> dotnet new --install Microsoft.AspNetCore.SpaTemplates::*
```

Once the templates have been installed, the output will look like the following:
```bash
--------------------------------------------------------------------------------------------------------
Console Application                               console          [C#], F#, VB      Common/Console
Class library                                     classlib         [C#], F#, VB      Common/Library
Unit Test Project                                 mstest           [C#], F#, VB      Test/MSTest
xUnit Test Project                                xunit            [C#], F#, VB      Test/xUnit
ASP.NET Core Empty                                web              [C#], F#          Web/Empty
ASP.NET Core Web App (Model-View-Controller)      mvc              [C#], F#          Web/MVC
ASP.NET Core Web App                              razor            [C#]              Web/MVC/Razor Pages
ASP.NET Core with Angular                         angular          [C#]              Web/MVC/SPA
ASP.NET Core with React.js                        react            [C#]              Web/MVC/SPA
ASP.NET Core with React.js and Redux              reactredux       [C#]              Web/MVC/SPA
ASP.NET Core Web API                              webapi           [C#], F#          Web/WebAPI
global.json file                                  globaljson                         Config
NuGet Config                                      nugetconfig                        Config
Web Config                                        webconfig                          Config
Solution File                                     sln                                Solution
Razor Page                                        page                               Web/ASP.NET
MVC ViewImports                                   viewimports                        Web/ASP.NET
MVC ViewStart                                     viewstart                          Web/ASP.NET

Examples:
    dotnet new mvc --auth Individual
    dotnet new react
    dotnet new --help

C:\Projects\aspnet-core-spa>
```

### Alternative: Creating a SPA via Yeoman

```bash
C:\Projects\aspnet-core-spa>npm install -g yo generator-aspnetcore-spa
```

### Installing templates via yo

```bash
$>yo aspnetcore-spa
```

Note: Yeoman is now deprecated and no longer maintained after the release of dotnet core 2.0

### Install the SPA framework

Create a new folder, C:\Projects\aspnet-core-spa\aspnet-core-angular> and run the following command
```bash
$>dotnet new angular
```

Then go to the directory and run

```bash
C:\Projects\aspnet-core-spa\aspnet-core-angular>dotnet restore
```

```bash
C:\Projects\aspnet-core-spa\aspnet-core-angular>npm install
```

After the installation is complete, run the application using: 

```bash
C:\Projects\aspnet-core-spa\aspnet-core-angular>dotnet run
```

## Streamling the Dev Experience

### Webpack Dev Middleware

* Webpack helps to bundle your scripts/images/styles/assets, modules with dependencies are bundled into static assets
* Don't have to run webpack manually
* Browser received up-to-date build output
* Build artifacts server instantly
* An instance of webpack stays active and has partial compilation states pre-cached in memory

### Setting up ASP.NET core in Dev Mode with Environment Variable

If you're using PowerShell then go to the folder
```bash
C:\Projects\ps\aspnet-core-spa\aspnet-core-angular>$Env:ASPNETCORE_ENVIRONMENT = "Development"
```

or use this:

```bash
C:\Projects\ps\aspnet-core-spa>setx ASPNETCORE_ENVIRONMENT "Development"
```
will result in:

```md
C:\Projects\ps\aspnet-core-spa>setx ASPNETCORE_ENVIRONMENT "Development"

SUCCESS: Specified value was saved.

C:\Projects\aspnet-core-spa>
```

You can verify by using:

```bash
C:\Projects\ps\aspnet-core-spa>echo ASPNETCORE_ENVIRONMENT=Development
ASPNETCORE_ENVIRONMENT=Development
```

```bash
C:\Projects\ps\aspnet-core-spa>echo %ASPNETCORE_ENVIRONMENT%
Development
```

Make sure to install the latest verson of Webpack

```bash
$>npm install webpack@latest
```

Then
```bash
C:\Projects\aspnet-core-spa\aspnet-core-angular>webpack
(node:24748) DeprecationWarning: Tapable.plugin is deprecated. Use new API on `.hooks` instead
Hash: 54fd112c01670d37adbee65c551dc6efd2add5b3
Version: webpack 4.16.0
Child
    Hash: 54fd112c01670d37adbe
    Time: 10784ms
    Built at: 2018-07-13 13:37:56
                 Asset      Size  Chunks             Chunk Names
        main-client.js  22.5 KiB       0  [emitted]  main-client
    main-client.js.map  89.4 KiB       0  [emitted]  main-client

    WARNING in configuration
    The 'mode' option has not been set, webpack will fallback to 'production' for this value. Set 'mode' option to 'development' or 'production' to enable defaults for each environment.
    You can also set it to 'none' to disable any default behavior. Learn more: https://webpack.js.org/concepts/mode/
Child
    Hash: e65c551dc6efd2add5b3
    Time: 16489ms
    Built at: 2018-07-13 13:38:02
             Asset      Size  Chunks             Chunk Names
    main-server.js  1.61 MiB       0  [emitted]  main-server

    WARNING in configuration
    The 'mode' option has not been set, webpack will fallback to 'production' for this value. Set 'mode' option to 'development' or 'production' to enable defaults for each environment.
    You can also set it to 'none' to disable any default behavior. Learn more: https://webpack.js.org/concepts/mode/

C:\Projects\aspnet-core-spa\aspnet-core-angular>
```

Build the project:

```bash
$>dotnet build
```

Run the project:

```bash
$>dotnet run
```

### Hot Module Replacement

* Watches for any changes to source files
| -.ts / .html / .sass

* Seperate NPM module
| $> npm install --save webpack-hot-middleware

## Installing ASP.NET Core with React and Redux

```bash
$> dotnet new reactredux
```

Once the installation is completed, run the following command:
```bash
$> npm install
```

* Add the Redux DevTools in Chrome browser