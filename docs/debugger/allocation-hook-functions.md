---
title: 分配挂钩函数 |Microsoft 文档
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
- memory allocation, logging allocation information
- insufficient memory
- debugging [C++], hook functions
- _CrtSetAllocHook function
- allocation hooks
- hooks, allocation
ms.assetid: 6bfbdb65-8cb1-4c21-8c45-7194a2b77c1e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c46b498ea36459dff0eb538ac3e0371fd9c5707
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31460103"
---
# <a name="allocation-hook-functions"></a>分配挂钩函数
分配挂钩函数，使用安装[_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook)，每次分配、 重新分配或释放内存时调用。 该类型的挂钩可用于很多不同用途。 例如，可用它测试应用程序处理内存不足情况的方式，检查分配模式，或记录分配信息以供将来分析。  
  
> [!NOTE]
>  请注意有关在分配挂钩函数中, 所述使用 C 运行时库函数的限制[分配挂钩和 C 运行时内存分配](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)。  
  
 分配挂钩函数应有类似下面的原型：  
  
```  
int YourAllocHook(int nAllocType, void *pvData,  
        size_t nSize, int nBlockUse, long lRequest,  
        const unsigned char * szFileName, int nLine )  
```  
  
 指针传递给[_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook)属于类型 **_CRT_ALLOC_HOOK**，如 CRTDBG 中定义。H:  
  
```  
typedef int (__cdecl * _CRT_ALLOC_HOOK)  
    (int, void *, size_t, int, long, const unsigned char *, int);  
```  
  
 当运行时库调用您的挂钩， *nAllocType*参数用于指示哪些分配即将执行的操作 (**_HOOK_ALLOC**， **_HOOK_REALLOC**，或 **_HOOK_FREE**)。 在释放或重新分配的情况下，`pvData` 包含指向将释放块的用户主题的指针。 但在分配情况下，该指针为空，因为分配尚未发生。 剩余的自变量包含所讨论分配的大小、其块类型、与它关联的顺序请求编号，以及指向在其中进行分配的文件名和行号的指针（如果有）。 挂钩函数执行所有分析及其他任务其作者需要后，它必须返回**TRUE**，指示分配操作可以继续，或**FALSE**，以指示，操作应失败。 检查目前为止，分配的内存量，则返回此类型的简单挂钩可能**FALSE**如果该数量超出小限制。 然后应用程序将经历分配错误，这种错误通常只会在可用内存极为不足时发生。 较复杂的挂钩可以跟踪分配模式，分析内存使用，或在特定情况发生时进行报告。  
  
## <a name="see-also"></a>请参阅  
 [分配挂钩和 C 运行时内存分配](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)   
 [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)   
