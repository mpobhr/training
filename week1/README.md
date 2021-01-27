# Introduction to web application development

## Development setup
* .NET 5.0 SDK:
    * [Download](https://dotnet.microsoft.com/download/dotnet/5.0)
    * `$ dotnet --version`
    
* Visual Studio Code:
    * [Download](https://code.visualstudio.com/download)
    * `$ code `
* Git 
    * [Download](https://git-scm.com/)
    * `$ git`
* [REPL](https://sharplab.io)
    

## NET 5.0
It is Microsoft Technology to improve experience creating application. Net 5.0 provide better type safety and memory management compare with low level programming language such as C/C++ and provide better analysis compare to scripting language like JS.
* Type Safety:
    * Prevent Stack overflow.
    * Avoid runtime crash.
    * Guard from possible system corruption.
* Memory Management:
    * Manual memory management.
    * Automatic memory management with Garbage Collector (GC).
* Analysis
    * Reduce possible runtime error.
    * Dead code elimination.
    * Warning and suggestion for better code.

.NET 5.0 consist of 
* Common Language Runtime (CLR)
    * OS Independent, Abstract common Process
    * Running CIL process
    * Handle type safety
    * Manage memory (GC)
    * Just in Time Compilation (optimize code)
    * Profile Guided Optimization (PGO)
* Common Intermediated Language (CIL)
    * Cross Platform instruction representation (improve ASM)
    * Multiple language support (C#, VB, F#)
* CoreFX
    * Collection of Library 
    * Simplify common uses case

## Introduction to C# Programming Language 
* Most used language in .NET 5.0 based C/C++ syntax.
* `struct` as Value type as primitive type `byte, int, float, double`
* `class` as Reference Type which based on `System.Object`
* Object oriented with single inherited for class
* Interface for contract / template implementation
* Multiple inherited for Interface
* Namespace for separation of multiple class

## .NET 5.0 SDK Command Line Interface
* Create Project
* Build Project
* Run Project
* Publish Project
* Add or Restore Package

## Introduction to Visual Studio Code
* Cross platform editor based on Electron
* uses for web development center around javascript
* Excellent C# Editor with Limited IDE capability
* WSL and Remote Linux Project

## Introduction to Git Source Control Management
* Decentralize Source Control Management
* Record code history and changes and involved files
* Allow multiple people work on same code
* Allow multiple version within same repository
* Better handling multiple version, with branching
* Init Repo, Staging, Commit, History, Remote, Push, Pull,Sync, Blame


## Introduction to Visual Studio 2019 (Community Edition)
* Full fledge IDE for better development experience
* Multiple Programming Language support
* Multiple Platform Support
* Command Line, Desktop, Mobile, Cloud, IoT

## Introduction to AspNetCore 5.0
* Cross platform C# Web Application Framework
* Cloud ready with micro services
* High Performance [Benchmark](https://www.techempower.com/benchmarks/#section=data-r19&hw=ph&test=plaintext)
* Support low level web application
* Razor Page (Model View View Model - MVVM), Model View Controller (MVC), Web API for services, Blazor for Client Side.
