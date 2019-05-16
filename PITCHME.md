---
marp: true
title: 
description: .NET Core, Sdk, Msbuild, `dotnet` CLI
footer: Amadeusz Sadowski © 2019
theme: uncover
paginate: true
auto-scaling: true
---

# Modern .NET

How to benefit from .NET Core, .NET Standard, MSBuild v15+, `dotnet` CLI, Sdk-style `.csproj`, .NET Local/Global Tools and a hint of what's coming.

<!--
Remind people to install .NET Core SDK (v2.2, check if they have Visual Studio Code, Omnisharp extension)
https://docs.microsoft.com/en-gb/dotnet/core/tutorials/with-visual-studio-code
-->

---

# What is all that about

It's about having a:
- Cross-platform,
- Open-source,
- Community-inclusive,
- and just simply *awesome*

**🛠-set**

---

### .NET Framework

<!-- Play: https://youtu.be/moSFlvxnbgk (Frozen - Let it go) -->

![Let it go meme](https://memegenerator.net/img/instances/x300/52425229.jpg)

Visit https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/ for confirmation

---

# .NET Core

- Since November 2014
- Cross-platform
- No .NET Framework compatibility
- Supercharged (many back-compat bugs fixed)

---

# .NET Standard

- Portable Class Libraries were: complicated, thin-spread, problematic for targeting and poorly designed (as intersections of existing implementations)
- Streamlining API levels (backported for 1.x)
  - 1.0 - 1.6 (created for .NET Core 1.0)
  - 2.0 (.NET Framework 4.6.1+, .NET Core 2.0)
  - 2.1 *WIP* (.NET Core 3.0, ⚠ no Framework support)

---

# .NET Standard support

<!--
source: https://docs.microsoft.com/en-gb/dotnet/standard/net-standard

The following table lists the minimum platform versions that support each .NET Standard version. That means that later versions of a listed platform also support the corresponding .NET Standard version. For example, .NET Core 2.2 supports .NET Standard 2.0 and earlier.

-->
<style scoped> table { font-size: 0.7em } </style>

.NET Standard   | 1.0 | 1.1 | 1.2   | 1.3 | 1.4  | 1.5 | 1.6  | 2.0
|:-             |:-   |:-   |:-     |:-   |:-    |:-   |:-    |:-
.NET Core       | ➡   | ➡   | ➡     | ➡   | ➡    | ➡   | 1.0  | 2.0
.NET Framework  | ➡   | 4.5 | 4.5.1 | 4.6 | ➡    | ➡   | ➡    | 4.6.1
Mono            | ➡   | ➡   | ➡     | ➡   | ➡    | ➡   | 4.6  | 5.4
Xamarin.iOS     | ➡   | ➡   | ➡     | ➡   | ➡    | ➡   | 10.0 | 10.14
Xamarin.Mac     | ➡   | ➡   | ➡     | ➡   | ➡    | ➡   | 3.0  | 3.8
Xamarin.Android | ➡   | ➡   | ➡     | ➡   | ➡    | ➡   | 7.0  | 8.0
UWP             | ➡   | ➡   | ➡     | ➡   | 10.0 | ➡   | ➡    | 10.0.16299
Unity           | ➡   | ➡   | ➡     | ➡   | ➡    | ➡   | ➡    | 2018.1

---

# MSBuild 15+

- [Cross-platform](https://devblogs.microsoft.com/dotnet/msbuild-is-going-cross-platform-with-net-core/)
- Integrated with `dotnet` ➡ `dotnet msbuild`
- Supports:
  - `<PackageReference />` NuGet references with transient dependency support
  - Sdk-style `.csproj`
  - Cross-targeting (multi-targeting)
  - Wildcards: `Include="**/*.cs"`

<!--
See https://devblogs.microsoft.com/dotnet/net-core-tooling-in-visual-studio-15/ 
-->

---

# Sdk-style `csproj`

- [PR introducing Sdk-style `.csproj` to `Uno.Inventory.Software.Server`](https://ivanti.visualstudio.com/Uno/_git/Inventory.Software.Server/pullrequest/25602?_a=overview)
- 227 file changes:
  - 11 ➕
  - 137 ➖
  - 77 edits
  - 2 renames

---

# `dotnet` CLI

- Cross-platform, runs on .NET Core, extensible
- Supports `new`, `build`, `run` and more actions
- Single point of truth about .NET Core system-wide
- Supports Local and Global Tools

---

# `dotnet` CLI Tools

- [Deprecated "Per-project" tools](https://docs.microsoft.com/pl-pl/dotnet/core/tools/extensibility#per-project-based-extensibility)
- [Replaced with Sdk v3.0 Local Tools](https://github.com/dotnet/announcements/issues/107)
- Global Tools installed via `dotnet`:
  - e.g. `dotnet tool install -g dotnetsay`
- Local and Global tools are the same package, installed differently

---

# Example of possibilities

- [`Amadevus.RecordGenerator`](https://amis92.github.io/RecordGenerator/)
- [`wham` library](https://github.com/WarHub/wham/) - massive code generation

---

# What's to come

- .NET Core 3.0 (.NET Standard 2.1) - September 2019
  - Local Tools
  - EF 6.3
- C# 8.0
  - NNRTs (Non-Nullable Reference Types) - `string?`
  - Default implementations in interfaces
  - Index and Range `array[0..array.Length-1]`
- And in 2021 - [**.NET 5**](https://devblogs.microsoft.com/dotnet/introducing-net-5/)

---

### Q&A

---

# Workshop

<!-- Play https://youtu.be/V-zXT5bIBM0 (Frozen - Do You Want to Build a Snowman) -->

Let's build a **`dotnet` tool**

![do you wanna build a snowman gif](https://media.giphy.com/media/r8JjvUvQ7Zd4c/giphy.gif)

and raise your factor of being cool!

<!--
Bootstrapping
https://docs.microsoft.com/en-gb/dotnet/core/tutorials/with-visual-studio-code

-->

---

### Credits

Written in Markdown, presented with [Marpit](https://marpit.marp.app/)

---

### After-credits

Thank you!
