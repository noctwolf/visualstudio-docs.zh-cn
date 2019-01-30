---
title: DA0505：为所分析的进程分配的平均专用字节数 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0505
- vs.performance.rules.DA0505
- vs.performance.505
ms.assetid: 32c612ea-d077-44ba-8e6f-3a96333bad00
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 26a3678bb47a27152daa46488d756fe7d51abfa8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54929960"
---
# <a name="da0505-average-private-bytes-allocated-for-the-process-being-profiled"></a>DA0505：为所分析的进程分配的平均专用字节数

|||  
|-|-|  
|规则 ID|DA0505|  
|类别|资源管理|  
|分析方法|全部|  
|消息|收集此信息仅用于参考。 进程专用字节计数器测量由正在分析的进程分配的虚拟内存。 报告的值是针对所有测量时间间隔所计算的平均值。|  
|规则类型|信息|  

 使用采样法、.NET 内存或资源争用方法进行分析时，必须收集至少 10 个样本才能触发此规则。  

## <a name="rule-description"></a>规则说明  
 此消息用于报告进程当前已分配的虚拟内存的平均字节数（专用字节）。 专用字节表示由进程分配的虚拟内存位置，只能通过进程内部运行的线程访问此进程。  

 对于在 32 位计算机上运行的 32 位进程，进程地址空间专用部分的上限为 2 GB。 使用 [/3GB](http://go.microsoft.com/fwlink/?LinkId=177831) Boot.ini 开关，32 位进程最多可以获得 3 GB 的虚拟内存。 在 64 位计算机上运行的 32 位进程最多可以获得 4 GB 的专用虚拟内存。  

 在 64 位计算机上运行的 64 位进程最多可以获得 8 TB 的专用虚拟内存。  

 报告的值是所分析的进程处于活动状态的所有测量时间间隔的平均值。  

 有关进程地址空间的详细信息，请参阅 Windows 内存管理文档中的 [Virtual Address Space](http://go.microsoft.com/fwlink/?LinkId=177832)（虚拟地址空间）。  

## <a name="how-to-use-rule-data"></a>如何使用规则数据  
 若要了解不同分析方案中应用程序的性能，可使用报告的值比较不同版本程序的性能。