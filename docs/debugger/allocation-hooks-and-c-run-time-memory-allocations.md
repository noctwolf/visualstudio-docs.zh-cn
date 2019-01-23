---
title: 分配挂钩和 C 运行时内存分配 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 7e4c631b72ae9b12f77daf2ddd49919651c0b3e5
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433095"
---
# <a name="allocation-hooks-and-c-run-time-memory-allocations"></a>分配挂钩和 C 运行时内存分配
分配挂钩函数具有一个非常重要的限制，即这些函数必须显式忽略 `_CRT_BLOCK` 块。这些块是 C 运行时库函数内部进行的内存分配（如果它们对分配内部内存的 C 运行时库进行任何调用）。可以通过在分配挂钩函数的开头包含以下代码来忽略 `_CRT_BLOCK` 块：  
  
```cpp
if ( nBlockUse == _CRT_BLOCK )  
    return( TRUE );  
```  
  
 如果分配挂钩不忽略 `_CRT_BLOCK` 块，那么在挂钩函数中调用任何 C 运行时库函数，都可以使用程序陷入无限循环。例如，`printf` 执行内部分配。如果挂钩代码调用 `printf`，生成的内存分配将导致再次调用挂钩，从而再次调用 printf ，依此类推，直到堆栈溢出。如果需要报告 `_CRT_BLOCK` 分配内存操作，回避该限制的一种方法是，使用 Windows API 函数而不是 C 运行时函数来进行格式设置和输出。由于 Windows API 不使用 C 运行库堆，因此不会让分配挂钩陷入无穷循环****。  
  
 如果要检查运行时库源文件，则将看到默认的分配挂钩函数 CrtDefaultAllocHook (仅会返回“TRUE” )位于其自身的单独源文件 DBGHOOK.C 中。如果希望调用分配挂钩，即使对于在应用程序中的 main 函数之前执行的运行时代码所做的内存分配，也可以使用自己的其中一个函数来替换默认函数，而不是使用 [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook)************。  
  
## <a name="see-also"></a>请参阅  
 [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)   
