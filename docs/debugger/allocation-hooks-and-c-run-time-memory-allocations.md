---
title: 分配挂钩和 C 运行时内存分配 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], hook functions
- memory allocation, troubleshooting allocation hooks
- allocation hooks
- hooks, allocation
ms.assetid: cc34ee96-3d91-41bd-a019-aa3759139e7e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3f20c71ad12a64e6d8d14b91310c870477cfc6d4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53899621"
---
# <a name="allocation-hooks-and-c-run-time-memory-allocations"></a>分配挂钩和 C 运行时内存分配
对分配挂钩函数的一个非常重要限制是，它们必须显式忽略`_CRT_BLOCK`块。 这些块是如果它们调用任何分配内部内存的 C 运行时库函数内部进行由 C 运行时库函数的内存分配。 你可以忽略`_CRT_BLOCK`块，方法是包括在你分配的开始处的 folloiwng 代码挂钩函数：  
  
```cpp
if ( nBlockUse == _CRT_BLOCK )  
    return( TRUE );  
```  
  
 如果您的分配挂钩不忽略`_CRT_BLOCK`块，那么挂钩中调用任何 C 运行时库函数可以捕获程序进入无限循环。 例如，`printf` 执行内部分配。 如果挂钩代码调用 `printf`，则产生的分配将导致再次调用挂钩，而挂钩又再次调用 printf，如此继续直到堆栈溢出。 如果需要报告 `_CRT_BLOCK` 分配操作，回避该限制的一种方法是，使用 Windows API 函数而不是 C 运行时函数来进行格式化和输出。 因为 Windows Api 不使用 C 运行库堆，所以它们不会捕获您的分配挂钩陷入无穷循环。  
  
 如果检查运行库源文件，将看到默认分配挂钩函数 CrtDefaultAllocHook（只返回 TRUE）位于其自己的单独文件 DBGHOOK.C 中。 如果希望为运行时启动代码（在应用程序的主函数之前执行）进行的分配调用分配挂钩，可以用自己的函数替换此默认函数，而不使用 [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook)。  
  
## <a name="see-also"></a>请参阅  
 [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)   
