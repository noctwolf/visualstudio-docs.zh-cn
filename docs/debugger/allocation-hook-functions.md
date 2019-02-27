---
title: 分配挂钩函数 |Microsoft Docs
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
- memory allocation, logging allocation information
- insufficient memory
- debugging [C++], hook functions
- _CrtSetAllocHook function
- allocation hooks
- hooks, allocation
ms.assetid: 6bfbdb65-8cb1-4c21-8c45-7194a2b77c1e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bd2900544fe2c33cfaaf9d1a0da5d4ff1ac41ab4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616786"
---
# <a name="allocation-hook-functions"></a>分配挂钩函数
分配挂钩函数，使用安装[_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook)，每次分配、 重新分配或释放内存时调用。 这种类型的挂钩可用于多种用途。 使用它来测试应用程序如何处理内存不足的情况下，例如检查分配模式，或记录分配信息以供日后分析。

> [!NOTE]
>  注意有关在分配挂钩函数中使用 C 运行库函数的限制，详见[分配挂钩和 C 运行时内存分配](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)中的说明。

 分配挂钩函数应具有的原型如下例所示：

```cpp
int YourAllocHook(int nAllocType, void *pvData,
        size_t nSize, int nBlockUse, long lRequest,
        const unsigned char * szFileName, int nLine )
```

 传递给 [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook) 的指针为 _CRT_ALLOC_HOOK 类型，如 CRTDBG.H 中所定义：

```cpp
typedef int (__cdecl * _CRT_ALLOC_HOOK)
    (int, void *, size_t, int, long, const unsigned char *, int);
```

 当运行时库调用挂钩时，nAllocType 参数指示即将进行的分配操作（**_HOOK_ALLOC**， **_HOOK_REALLOC** 或 **_HOOK_FREE**)。 在释放或重新分配中，`pvData` 具有一个指向即将释放的块的用户文章的指针。 但是，对于分配，该指针为空，因为分配尚未发生。 其余参数包含所讨论的分配大小、其块类型、与其相关联的顺序请求编号以及指向文件名的指针。 如果可用，参数还包括在其中进行分配的行号。 挂钩函数执行完毕其作者需要的任何分析和其他任务后，它必须返回 TRUE，表示分配操作可以继续，或者返回 FALSE，表示操作会失败。 此类型的简单挂钩可以检查到目前为止分配的内存量，如果内存量超过了小限制，则返回 FALSE。 然后，应用程序会遇到通常只有在可用内存非常低时才会出现的分配错误。 更复杂的挂钩可能会跟踪分配模式，分析内存使用情况，或在特定情况发生时进行报告。

## <a name="see-also"></a>请参阅

- [分配挂钩和 C 运行时内存分配](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)
- [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)