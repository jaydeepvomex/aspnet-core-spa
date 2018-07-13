# Building ASP.NET Core to build Single-Page Applications

## Installing the Templates for .NET cli

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

## Alternative: Creating a SPA via Yeoman

```bash
C:\Projects\aspnet-core-spa>npm install -g yo generator-aspnetcore-spa
```

### Installing templates via yo

```bash
$>yo aspnetcore-spa
```

Note: Yeoman is now deprecated and no longer maintained after the release of dotnet core 2.0

## Install the SPA framework

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