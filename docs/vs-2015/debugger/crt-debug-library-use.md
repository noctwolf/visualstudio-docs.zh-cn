---
title: CRT 调试库使用 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- c.debug.runtime
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- /DEBUG linker option [C++]
- crtdbg.h file
- debug library
- MDd compiler option [C++]
- libraries, CRT debug library
- MTd compiler option [C++]
- LDd compiler function [C++]
- /MTd compiler option [C++]
- /MDd compiler option [C++]
- debugging [CRT], CRT debug library
- DEBUG linker option [C++]
- /LDd compiler function [C++]
ms.assetid: 464de16b-4215-4787-9bfa-921aaff9d9f4
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87b0923153d5e4d0a3c5e4eb33a97e31fd3b2802
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478719"
---
# <a name="crt-debug-library-use"></a>CRT 调试库使用
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CRT 调试库使用](https://docs.microsoft.com/visualstudio/debugger/crt-debug-library-use)。  
  
C 运行库提供广泛的调试支持。 若要使用 CRT 调试库之一，您必须与链接[/debug](http://msdn.microsoft.com/library/1af389ae-3f8b-4d76-a087-1cdf861e9103)和使用进行编译 **/MDd**， **/MTd**，或者 **/LDd**。  
  
## <a name="remarks"></a>备注  
 CRT 调试的主要定义和宏可在 CRTDBG.h 头文件中找到。  
  
 CRT 调试库中的函数编译带有调试信息 ([/Z7、 /Zd、 /Zi、 /ZI （调试信息格式）](http://msdn.microsoft.com/library/ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8))，不进行优化。 某些函数包含断言以验证传递给它们的参数，并且提供源代码。 使用此类源代码，可以单步执行 CRT 函数，以确认这些函数按预期方式工作并检查错误的参数或内存状态。 （某些 CRT 技术是专有技术，不提供用于异常处理、浮点和少数其他例程的源代码。）  
  
 安装 Visual C++ 时，可以选择在硬盘上安装 C 运行库源代码。 如果不安装源代码，将需要 CD-ROM 才能单步执行 CRT 函数。  
  
 可以使用的各种运行时库的详细信息，请参阅[C 运行时库](http://msdn.microsoft.com/library/a889fd39-807d-48f2-807f-81492612463f)。  
  
## <a name="see-also"></a>请参阅  
 [CRT 调试技术](../debugger/crt-debugging-techniques.md)   
 [/MD、/MT、/LD（使用运行时库）](http://msdn.microsoft.com/library/cf7ed652-dc3a-49b3-aab9-ad60e5395579)



