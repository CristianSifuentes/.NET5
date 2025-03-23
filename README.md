
# What's New in .NET 5

## 📚 Table of Contents

- [Overview](#overview)
- [Naming and Versioning](#naming-and-versioning)
- [What's New](#whats-new)
  - [C# 9 Features](#c-9-features)
  - [F# 5 Features](#f-5-features)
  - [Visual Basic Updates](#visual-basic-updates)
  - [System.Text.Json Enhancements](#systemtextjson-enhancements)
  - [Performance Improvements](#performance-improvements)
  - [Single File Apps and Trimming](#single-file-apps-and-trimming)
  - [Windows Arm64 Support](#windows-arm64-support)
  - [Source Generators](#source-generators)
- [Compatibility Notes](#compatibility-notes)
  - [.NET 5 vs .NET Framework](#net-5-vs-net-framework)
  - [.NET 5 vs .NET Standard](#net-5-vs-net-standard)
- [Breaking Changes](#breaking-changes)
  - [ASP.NET Core](#aspnet-core)
  - [Code Analysis](#code-analysis)
  - [Core .NET Libraries](#core-net-libraries)
  - [Cryptography](#cryptography)
  - [Entity Framework Core](#entity-framework-core)
  - [Globalization](#globalization)
  - [Interop](#interop)
  - [Networking](#networking)
  - [SDK](#sdk)
  - [Security](#security)
  - [Serialization](#serialization)
  - [Windows Forms](#windows-forms)
  - [WPF](#wpf)
- [Unported Technologies & Alternatives](#unported-technologies--alternatives)
- [See Also](#see-also)

---

## Overview

.NET 5 is the next major release after .NET Core 3.1. It unifies the .NET platform by replacing .NET Core while continuing to support cross-platform development. It does **not** replace the .NET Framework.

---

## Naming and Versioning

- Skipped version 4.x to avoid confusion with .NET Framework 4.x.
- Dropped "Core" from the name to establish .NET 5 as the main implementation of .NET.
- ASP.NET Core 5.0 and EF Core 5.0 retain the "Core" name to avoid confusion with legacy ASP.NET and EF versions.

---

## What's New

### C# 9 Features

- **Records**: Immutable reference types with value-based equality.
- **Relational Pattern Matching**: `and`, `or`, `not` logic in pattern matching.
- **Top-Level Statements**: Simplified syntax without `Main()`:
  ```csharp
  System.Console.Write("Hello world!");
  ```
- **Function Pointers**: Low-level interop features using `ldftn`, `calli`.

### F# 5 Features

- **Interpolated Strings**:
  ```fsharp
  let name = "David"
  let age = 36
  let message = $"{name} is {age} years old."
  ```
- **Typed Interpolation** (like `sprintf`):
  ```fsharp
  let message = $"%s{name} is %d{age} years old."
  ```

### Visual Basic Updates

No new language features, but new project templates supported:

| Project Type                         | `dotnet new` Parameter     |
|-------------------------------------|----------------------------|
| Console Application                 | `console`                  |
| Class Library                       | `classlib`                 |
| WPF App/Class/User Control Library  | `wpf`, `wpflib`, etc.      |
| Windows Forms App/Class Library     | `winforms`, `winformslib`  |
| Unit Test Projects (NUnit/xUnit)    | `mstest`, `nunit`, `xunit` |

### System.Text.Json Enhancements

- Handle circular references
- Serialize immutable types and `record`s
- Support fields and non-public properties
- Custom converters for `null`
- JsonSerializerOptions cloning & presets

### Performance Improvements

- **Garbage Collection**
- **System.Text.Json**
- **Regex**
- **Async ValueTask pooling**
- **Container size optimizations**

### Single File Apps and Trimming

- Compile app into a single binary.
- Trim unused libraries for smaller deployments.

### Windows Arm64 Support

- Native support for Windows on ARM64.
- Includes intrinsics and optimizations.

### Source Generators

- Run at compile-time to generate additional code.
- Examples include serialization, DI registration, etc.

---

## Compatibility Notes

### .NET 5 vs .NET Framework

.NET 5 is not a drop-in replacement for .NET Framework. Some technologies are not ported:

| Technology                     | Suggested Alternative                 |
|-------------------------------|---------------------------------------|
| Web Forms                     | ASP.NET Core Blazor/Razor Pages       |
| Windows Workflow Foundation   | Elsa Workflows                        |
| Windows Communication Foundation (WCF) | gRPC or CoreWCF (open-source)     |

### .NET 5 vs .NET Standard

- Use `net5.0` TFM for all .NET 5 projects.
- Use `netstandard2.0` only when sharing with .NET Framework/Core.

---

## Breaking Changes

(For brevity, all breaking change categories will be in a separate document if needed due to size)

See the official documentation:
- [Breaking Changes in .NET 5](https://learn.microsoft.com/dotnet/core/compatibility/5.0)

---

## Unported Technologies & Alternatives

| Technology                  | Status/Alternative                     |
|----------------------------|----------------------------------------|
| Web Forms                  | Blazor or Razor Pages                  |
| Windows Workflow (WF)      | Elsa Workflows                         |
| WCF (Windows-only Server)  | CoreWCF (open source) or gRPC          |

---

## See Also

- [.NET Downloads](https://dotnet.microsoft.com/download)
- [What's New in C# 9](https://learn.microsoft.com/dotnet/csharp/whats-new/csharp-9)
- [Introducing Source Generators](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators/)
- [Performance Improvements in .NET 5](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/)
- [Breaking Changes in .NET 5](https://learn.microsoft.com/dotnet/core/compatibility/5.0)

---
