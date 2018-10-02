---
title: 从命令行分析 ASP.NET Web 应用程序 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profiling ASP.NET applications
- profling tools,ASP.NET applications
ms.assetid: 897c00d5-5767-433b-a960-4a29c6023ede
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7dd299aac87a03009e39034a3e5282777419506c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484649"
---
# <a name="command-line-profiling-of-aspnet-web-applications"></a>从命令行分析 ASP.NET Web 应用程序
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[命令行分析 ASP.NET Web 应用程序的](https://docs.microsoft.com/visualstudio/profiling/command-line-profiling-of-aspnet-web-applications)。  
  
本部分介绍如下进程的步骤和选项：使用命令行中的 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具收集 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Web 应用程序的性能数据。  
  
> [!NOTE]
>  Windows 8 和 Windows Server 2012 中增强的安全功能需要以 Visual Studio 探查器在这些平台上收集数据的方式进行重大更改。 Windows 应用商店应用程序也需要新的收集技术。 请参阅 [Windows 8 和 Windows Server 2012 应用程序上的性能工具](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。  
  
## <a name="common-tasks"></a>常规任务  
  
|任务|相关内容|  
|----------|---------------------|  
|**轻松收集基本的 ASP.NET 分析数据：** 使用 **VSPerfASPNETCmd** 工具收集采样、检测、.NET 内存、争用或不具有配置要求的层交互数据，以及 **VSPerfCmd** 所需的 Internet 信息服务 (IIS) 重启。 **VSPerfASPNETCmd** 不允许收集额外数据或控制数据收集。 **注意：****VSPerfASPNETCmd** 是使用独立探查器分析 ASP.NET 网站的首选工具。|-   [使用 VSPerfASPNETCmd 进行快速网站分析](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)|  
|**收集应用程序统计信息：** 使用采样法收集性能统计信息。 采样数据适用于分析 CPU 使用率问题以及了解应用程序的常规性能特征。|-   [使用采样法收集应用程序统计信息](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**收集详细计时数据：** 使用检测方法收集详细计时信息。 检测数据可用于分析 IO 问题和精细分析应用程序方案。|-   [使用检测收集详细计时数据](../profiling/collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line.md)|  
|**收集 .NET 内存数据：** 使用采样法或检测法收集显示分配对象的大小和数量的 .NET 内存分配数据。 还可以收集对象生存期数据，此数据显示在每次垃圾回收生成中回收的对象的大小和数量。|-   [收集内存数据](../profiling/collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line.md)|  
|**收集并发数据：** 使用并发方法收集资源争用数据。 **注意：** Web 应用程序不支持收集线程活动和可视化数据。|-   [收集并发数据](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
|**添加层交互数据：** 可以添加有关 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Web 应用程序对 Microsoft [!INCLUDE[vstecado](../includes/vstecado-md.md)] 数据库进行的同步 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 调用的性能数据。|-   [收集层交互数据](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>相关任务  
  
|任务|相关内容|  
|----------|---------------------|  
|**分析独立（客户端）应用程序**|-   [分析独立应用程序](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**分析服务**|-   [分析服务](../profiling/command-line-profiling-of-services.md)|



