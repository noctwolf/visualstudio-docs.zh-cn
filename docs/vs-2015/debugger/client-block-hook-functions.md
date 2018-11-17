---
title: 客户端块挂钩函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- client blocks, validating and reporting data
- debugging [C++], hook functions
- _CrtSetDumpClient function
- client blocks, hook functions
- hooks, client block
ms.assetid: f21c197e-565d-4e3f-9b27-4c018c9b87fc
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b16dc9eaff974e98e411d4f49d8aed6f9f656e8
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51773933"
---
# <a name="client-block-hook-functions"></a>客户端块挂钩函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

如果想要验证或报告存储在 `_CLIENT_BLOCK` 块中的数据的内容，可以专为此目的编写函数。 如同 CRTDBG.H 中所定义的，所编写的函数必须有与下面类似的原型：  
  
```  
void YourClientDump(void *, size_t)  
  
```  
  
 换而言之，您的挂钩函数应接受**void**一起使用的分配块的开头的指针**size_t**类型值，该值指示分配的大小和返回`void`. 除此之外，其内容由您决定。  
  
 安装挂钩函数使用后[_CrtSetDumpClient](http://msdn.microsoft.com/library/f3dd06d0-c331-4a12-b68d-25378d112033)，则将调用每次`_CLIENT_BLOCK`转储块。 然后，可以使用[_CrtReportBlockType](http://msdn.microsoft.com/library/0f4b9da7-bebb-4956-9541-b2581640ec6b)以获取有关转储块的子类型的类型信息。  
  
 指向传递给函数的指针`_CrtSetDumpClient`属于类型 **_CRT_DUMP_CLIENT**CRTDBG 中定义。H:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  
  
## <a name="see-also"></a>请参阅  
 [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 示例](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](http://msdn.microsoft.com/library/0f4b9da7-bebb-4956-9541-b2581640ec6b)



