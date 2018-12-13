---
title: Performance Diagnostics Tools
author: mjrousos
description: Useful tools for diagnosing performance issues in ASP.NET Core apps.
monikerRange: '>= aspnetcore-1.1'
ms.author: riande
ms.date: 12/07/2018
uid: performance/diagnostic-tools
---
# Performance Diagnostic Tools

By [Mike Rousos](https://github.com/mjrousos)

This article lists tools for diagnosing performance issues in ASP.NET Core.

## Visual Studio Diagnostic Tools

The [profiling and diagnostic tools](/visualstudio/profiling) built into Visual Studio are a good place to start investigating performance issues. These tools are powerful and convenient to use from the Visual Studio development environment. The tooling allows analysis of CPU usage, memory usage, and performance events in ASP.NET Core apps.

More information is available in [Visual Studio documentation](/visualstudio/profiling/profiling-overview).

## Application Insights

[Application Insights](/azure/application-insights/app-insights-overview) provides in-depth performance data for your app. Application Insights automatically collects data on response rates, failure rates, dependency response times, and more. Application Insights supports logging custom events and metrics specific to your app.

Application Insights can be used in a variety environments:

* Optimized to work in Azure.
* Works in production, development, and staging.
* Works locally from [Visual Studio](/azure/application-insights/app-insights-visual-studio) or in other hosting environments.

For more information, see [Application Insights for ASP.NET Core](/azure/application-insights/app-insights-asp-net-core).

## PerfView

[PerfView](https://github.com/Microsoft/perfview) is a performance analysis tool created by the .NET team specifically for diagnosing .NET performance issues. PerfView allows analysis of CPU usage, memory and GC behavior, performance events, and wall clock time.

You can learn more about PerfView and how to get started with [PerfView video tutorials](http://channel9.msdn.com/Series/PerfView-Tutorial) or by reading the user's guide available in the tool or [on GitHub](https://github.com/Microsoft/perfview).

## PerfCollect

While PerfView is a useful performance analysis tool for .NET scenarios, it only runs on Windows so you can't use it to collect traces from ASP.NET Core apps running in Linux environments.

[PerfCollect](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/linux-performance-tracing.md) is a bash script that uses native Linux profiling tools ([Perf](https://perf.wiki.kernel.org/index.php/Main_Page) and [LTTng](https://lttng.org/)) to collect traces on Linux that can be analyzed by PerfView. PerfCollect is useful when performance problems show up in Linux environments where PerfView can't be used directly. Instead, PerfCollect can collect traces from .NET Core apps that are then analyzed on a Windows computer using PerfView.

More information about how to install and get started with PerfCollect is available [on GitHub](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/linux-performance-tracing.md).