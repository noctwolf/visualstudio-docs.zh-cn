---
title: "收集其他性能数据 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 913f5043cf02f2fe78ffeefa83d5fd185740eb4c
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2018
---
# <a name="collecting-additional-performance-data"></a>收集其他性能数据

除使用分析方法收集的数据外，Visual Studio 分析工具还使你能够记录和查看其他数据。

## <a name="common-tasks"></a>常规任务

|任务|相关的内容|
|----------|---------------------|
|**收集应用程序中 ADO.NET 调用的性能数据。** 添加有关应用程序对数据库执行的同步调用的数据。|- [收集层交互数据](../profiling/collecting-tier-interaction-data.md)|
|**收集 Windows 性能计数器数据。** 将系统性能计数器作为分析标记添加到分析数据中。 标记可用于筛选报表。|- [如何：收集 Windows 计数器数据](../profiling/how-to-collect-windows-counter-data.md)|
|**收集 Windows 事件跟踪数据。** 收集 Windows 事件跟踪 (ETW) 数据，从而记录应用程序和系统事件，但不记录分析数据。|- [如何：收集 Windows 事件跟踪 (ETW) 数据](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|