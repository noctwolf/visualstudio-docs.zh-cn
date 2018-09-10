---
title: 报表挂钩函数 |Microsoft Docs
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
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 97d39a171d812915a1cf3c1c6450c73098067949
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44284193"
---
# <a name="report-hook-functions"></a>报表挂钩函数
使用安装的报表挂钩函数[_CrtSetReportHook](/cpp/c-runtime-library/reference/crtsetreporthook)，每次调用[_CrtDbgReport](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw)生成调试报告。 可以使用报告挂钩函数以及其他项筛选报告以集中于特定类型的分配。 报告挂钩函数应具有如下原型：  
  
```cpp
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 将指针传递给 **_CrtSetReportHook**属于类型 **_CRT_REPORT_HOOK**CRTDBG 中定义。H:  
  
```cpp
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 当运行库调用您的挂钩函数*nRptType*参数中包含的报表的类别 (**_CRT_WARN**， **_CRT_ERROR**，或 **_CRT_ASSERT**)， *szMsg*包含的全组装型的报告消息字符串、 指针和*retVal*指定是否`_CrtDbgReport`应继续正常执行后生成的报表或启动调试器。 (A *retVal*值为零继续执行，值为 1 启动调试器。)  
  
 如果挂钩完全处理了所涉及的消息，以便无报告要求，它应返回 **，则返回 TRUE**。 如果它返回**FALSE**，`_CrtDbgReport`通常情况下将报告消息。  
  
## <a name="see-also"></a>请参阅  
 [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 示例](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)
