---
title: 堆分配函数的调试版本 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.crt
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- debugging [CRT], heap allocation functions
- debugging memory leaks, CRT debug library functions
- malloc function
- memory leaks, CRT debug library functions
- heap allocation, debug
- _malloc_dbg function
ms.assetid: 91748bdc-f4cd-4d8b-ab98-0493dab7ed0d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f7df6a0ebc161d794a39e9e16b3b73abe42c6ec7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53862404"
---
# <a name="debug-versions-of-heap-allocation-functions"></a>堆分配函数的“Debug”版本
C 运行库包含堆分配函数的特殊“Debug”版本。 这些函数的名称与发行版本相同，只是追加了“_dbg”。 本主题用 `malloc` 和 `_malloc_dbg` 作为示例，描述 CRT 函数的发行版本和 _dbg 版本之间的差异。  
  
 当[_DEBUG](/cpp/c-runtime-library/debug)是定义，CRT 映射所有[malloc](/cpp/c-runtime-library/reference/malloc)调用[_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg)。 因此，不需要用 `_malloc_dbg` 代替 `malloc` 来重写代码以获得调试时的好处。  
  
 但您可能希望显式调用 `_malloc_dbg`。 显式调用 `_malloc_dbg` 具有一些附加的好处：  
  
- 跟踪 `_CLIENT_BLOCK` 类型分配。  
  
- 存储分配请求所在的源文件和行号。  
  
  如果不希望将您`malloc`调用`_malloc_dbg`，可以通过定义获取源文件信息[_CRTDBG_MAP_ALLOC](/cpp/c-runtime-library/crtdbg-map-alloc)，这将导致预处理器将对直接映射到的所有调用`malloc`到`_malloc_dbg`而不是依靠周围的包装器`malloc`。  
  
  若要跟踪客户端块中各种类型的分配，必须直接调用 `_malloc_dbg`，并将 `blockType` 参数设置为 `_CLIENT_BLOCK`。  
  
  未定义 _DEBUG，调用`malloc`不受干扰，而对调用`_malloc_dbg`将解析为`malloc`，定义[_CRTDBG_MAP_ALLOC](/cpp/c-runtime-library/crtdbg-map-alloc)被忽略，并且源与相关的文件信息未提供分配请求。 因为 `malloc` 没有块类型参数，所以将对 `_CLIENT_BLOCK` 类型的请求作为标准分配处理。  
  
## <a name="see-also"></a>请参阅  
 [CRT 调试方法](../debugger/crt-debugging-techniques.md)