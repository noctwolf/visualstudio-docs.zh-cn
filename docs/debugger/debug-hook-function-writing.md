---
title: 编写调试挂钩函数 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 365196a01ba9e62ef0b26eb3a99278d4d77a4dd4
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31457337"
---
# <a name="debug-hook-function-writing"></a>编写调试挂钩函数
本节描述了你可以编写的自定义调试挂钩函数，它允许你在调试器的正常处理中将代码插入某些预定义的点中。  
  
## <a name="in-this-section"></a>本节内容  
 [客户端块挂钩函数](../debugger/client-block-hook-functions.md)  
 提供有关编写某些函数的指导和原型，这些函数验证或报告正存储在 _CLIENT_BLOCK 块中的数据的内容。  
  
 [分配挂钩函数](../debugger/allocation-hook-functions.md)  
 定义分配挂钩函数，探讨它的不同用法，指出限制并提供原型。  
  
 [分配挂钩和 CRT 内存分配](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)  
 描述分配挂钩函数在调用分配内部内存的 C 运行库函数时，在显式忽略 `_CRT_BLOCK` 块方面所受的限制。 本主题还列出将出现哪些后果，如果您的分配挂钩未忽略`_CRT_BLOCK`（有示例） 的数据块以及如何更改默认分配挂钩函数， **CrtDefaultAllocHook**。  
  
 [报表挂钩函数](../debugger/report-hook-functions.md)  
 讨论 `_CrtSetReportHook`，可以使用它筛选报告以集中于特定的分配类型。 本主题还提供原型。  
  
## <a name="related-sections"></a>相关章节  
 [CRT 调试方法](../debugger/crt-debugging-techniques.md)  
 链接到 C 运行库的调试技术，包括：使用 CRT 调试库、用于报告的宏、`malloc` 和 `_malloc_dbg` 之间的差异、编写调试挂钩函数以及 CRT 调试堆。