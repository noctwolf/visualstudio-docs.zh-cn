---
title: Sys (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb87886e4b40643a23e661294c6fcf0a2a74332b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480770"
---
# <a name="sys-vsperfcmd"></a>Sys (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Sys (VSPerfCmd)](https://docs.microsoft.com/visualstudio/profiling/sys-vsperfcmd)。  
  
VSPerfCmd.exe **Sys** 选项将采样的分析事件设置为系统调用事件（被分析的应用程序中对操作系统的函数调用），还可以选择将采样间隔内的系统调用数从默认值 10 改为其他值。  
  
 只能在包含 **Launch** 或 **Attach** 选项的命令行中使用 **Sys**。  
  
 默认情况下，将探查器采样事件设置为处理器时钟周期，并将采样间隔设置为 10,000,000。 使用 **Timer**、**PF**、**Sys** 和 **Counter** 选项可以设置采样事件和采样间隔。 **GC** 选项在每次发生分配和垃圾回收事件时收集 .NET 内存数据。 在命令行中只能指定这些选项中的一个。  
  
 只能在包含 **Launch** 或 **Attach** 选项的第一个命令行中设置采样事件和采样间隔。  
  
## <a name="syntax"></a>语法  
  
```  
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]  
```  
  
#### <a name="parameters"></a>参数  
 `Events`  
 一个整数值，指定采样间隔内系统调用事件的数量。 如果未指定 `Events`，则将间隔设置为 10。  
  
## <a name="required-options"></a>必需选项  
 **Sys** 要求使用以下选项之一。  
  
 **Launch：**`AppName`  
 启动探查器以及由 `AppName` 指定的应用程序。  
  
 **Attach:** `PID`  
 将探查器附加到 `PID` 指定的进程。  
  
## <a name="invalid-options"></a>无效选项  
 不能在 **Sys** 所在的命令行中指定以下选项。  
  
 **PF**[**:**`Events`]  
 将采样事件设置为页面错误，根据需要还可以将采样间隔设置为 `Events`。 默认 PF 间隔为 10。  
  
 **Timer**[**:**`Cycles`]  
 将采样事件设置为处理器时钟周期，还可以选择将采样间隔设置为 `Cycles`。 默认 Timer 间隔为 10,000,000。  
  
 **Counter:** `Name`[`,Reload`[`,FriendlyName`]]  
 将采样事件设置为 `Name` 指定的 CPU 性能计数器，并将采样间隔设置为 `Reload`。  
  
 **GC**[**:**{**Allocation**&#124;**Lifetime**}]  
 收集 .NET 内存数据。 默认情况 (Allocation) 下，每次发生内存分配事件时都收集数据。 如果指定 Lifetime 参数，则每次发生垃圾回收事件时也收集数据。  
  
## <a name="example"></a>示例  
 本示例演示如何将探查器采样事件设置为系统调用，以及如何将采样间隔设置为每个样本 20 次调用。  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20  
```  
  
## <a name="see-also"></a>请参阅  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [分析独立应用程序](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [分析 ASP.NET Web 应用程序](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [分析服务](../profiling/command-line-profiling-of-services.md)



