---
title: 从命令行使用分析方法收集性能数据 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 5613fafc-f298-4e7a-9a2d-a853b61cdf9c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 141341c09d9028e90900a29c702667304cfea7f7
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34477700"
---
# <a name="use-profiling-methods-to-collect-performance-data-from-the-command-line"></a>使用分析方法通过命令行收集性能数据
选择的 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 分析工具命令行工具和选项取决于各种因素，如进行分析的应用程序的类型、要使用的分析方法以及是以本机还是 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 代码编码目标应用程序。  
  
 本主题根据选择的分析方法组织命令行过程主题。  
  
## <a name="use-the-sampling-method-to-collect-performance-statistics"></a>使用采样方法收集性能统计信息  
 分析工具采样方法在分析运行中按指定间隔收集性能数据。 采样数据可以提供对占用大量 CPU 的性能问题的深入了解，并且可以是开始探索应用程序性能的好办法。  
  
 可以同时启动探查器和应用程序，也可以将探查器附加到正在运行的应用程序实例。  
  
|任务|目标应用程序类型|  
|----------|-----------------------------|  
|**启动应用程序**|-   [独立应用程序](../profiling/how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line.md)|  
|**附加到正在运行的进程**|-   [.NET Framework 独立应用程序](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-application-statistics.md)<br />-   [本机独立应用程序](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)<br />-   [ASP.NET Web 应用程序](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [.NET 服务](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [本机服务](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="use-the-instrumentation-method-to-collect-detailed-timing-data"></a>使用检测方法收集详细计时数据  
 分析工具检测方法从包含软件探测的应用程序二进制文件副本收集性能数据，以记录性能信息。 会在每个检测的函数开始和结束时，以及在每次从检测的函数调用其他函数时收集检测数据。 检测方法可用于发现与 I/O 问题有关的性能问题（如磁盘使用率）。  
  
 可使用 [VInstr.exe](../profiling/vsinstr.md) 工具创建检测的二进制文件。 初始化探查器之后，会在运行目标应用程序时自动从检测的二进制文件收集数据。  
  
 **目标应用程序类型**  
  
-   [.NET Framework 独立组件](../profiling/how-to-instrument-a-stand-alone-dotnet-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [本机独立组件](../profiling/how-to-instrument-a-native-stand-alone-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [静态编译的 ASP.NET Web 应用程序](../profiling/how-to-instrument-statically-compiled-aspnet-and-collect-detailed-timing-data.md)  
  
-   [动态编译的 ASP.NET Web 应用程序](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)  
  
-   [.NET 服务](../profiling/how-to-instrument-a-dotnet-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
-   [本机服务](../profiling/how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
## <a name="use-net-memory-methods-to-collect-memory-allocation-and-object-lifetime-data"></a>使用 .NET 内存方法收集内存分配数据和对象生存期数据  
 分析工具 .NET 内存方法使你可以收集有关 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 中的对象生存期的 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 内存分配数据和信息。  
  
 可以使用探查器启动目标应用程序；可以将探查器附加到正在运行的应用程序实例；并且可以创建应用程序的受检测版本以收集详细计时信息以及 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 内存数据。  
  
|任务|目标应用程序类型|  
|----------|-----------------------------|  
|**启动应用程序**|-   [独立 .NET Framework 应用程序](../profiling/how-to-launch-a-stand-alone-dotnet-framework-application-with-the-profiler-to-collect-memory-data-by-using-the-command-line.md)|  
|**附加到正在运行的进程**|-   [.NET Framework 独立应用程序](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [ASP.NET Web 应用程序](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [.NET 服务](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-memory-data-by-using-the-command-line.md)|  
|**检测模块**|-   [.NET Framework 独立组件](../profiling/how-to-instrument-a-dotnet-framework-component-and-collect-memory-data.md)<br />-   [静态编译的 ASP.NET Web 应用程序](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)<br />-   [动态编译的 ASP.NET Web 应用程序](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)<br />-   [.NET 服务](../profiling/how-to-instrument-a-dotnet-framework-service-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
  
## <a name="use-the-concurrency-method-to-collect-resource-contention-and-thread-activity-data"></a>使用并发方法收集资源争用数据和线程活动数据  
 分析工具并发方法使你可以从多线程应用程序收集资源争用以及线程和进程活动数据。  
  
 可以使用探查器启动应用程序，也可以将探查器附加到正在运行的应用程序实例。  
  
|任务|目标应用程序类型|  
|----------|-----------------------------|  
|**启动应用程序**|-   [独立 .NET Framework 应用程序](../profiling/how-to-launch-a-stand-alone-dotnet-framework-app-to-collect-concurrency-data.md)<br />-   [独立本机应用程序](../profiling/how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**附加到正在运行的进程**|-   [.NET Framework 独立应用程序](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-concurrency-data.md)<br />-   [本机独立应用程序](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-concurrency-data-by-using-the-command-line.md)<br />-   [ASP.NET Web 应用程序](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [.NET 服务](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [本机服务](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="add-tier-interaction-data-to-a-profiling-run"></a>将层交互数据添加到分析运行  
 若要将层交互数据添加到分析运行，需要使用命令行分析工具执行特定的步骤。 请参阅[收集层交互数据](../profiling/adding-tier-interaction-data-from-the-command-line.md)  
  
## <a name="see-also"></a>请参阅  
 [分析独立应用程序](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [分析 ASP.NET Web 应用程序](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [分析服务](../profiling/command-line-profiling-of-services.md)