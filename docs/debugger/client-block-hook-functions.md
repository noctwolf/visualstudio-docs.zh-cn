---
title: 客户端块挂钩函数 |Microsoft Docs
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
- client blocks, validating and reporting data
- debugging [C++], hook functions
- _CrtSetDumpClient function
- client blocks, hook functions
- hooks, client block
ms.assetid: f21c197e-565d-4e3f-9b27-4c018c9b87fc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee0209c082185e111988e5f8e39f2f0b806a4995
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433114"
---
# <a name="client-block-hook-functions"></a>客户端块挂钩函数
如果想要验证或报告存储在 `_CLIENT_BLOCK` 块中的数据的内容，可以专为此目的编写函数。 如同 CRTDBG.H 中所定义的，所编写的函数必须有与下面类似的原型：  
  
```cpp
void YourClientDump(void *, size_t)  
  
```  
  
 换而言之，您的挂钩函数应接受**void**一起使用的分配块的开头的指针**size_t**类型值，该值指示分配的大小和返回`void`. 除此之外，其内容由您决定。  
  
 安装挂钩函数使用后[_CrtSetDumpClient](/cpp/c-runtime-library/reference/crtsetdumpclient)，则将调用每次`_CLIENT_BLOCK`转储块。 然后，可以使用[_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype)以获取有关转储块的子类型的类型信息。  
  
 指向传递给函数的指针`_CrtSetDumpClient`属于类型 **_CRT_DUMP_CLIENT**CRTDBG 中定义。H:  
  
```cpp
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  
  
## <a name="see-also"></a>请参阅  
 [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 示例](http://msdn.microsoft.com/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype)
