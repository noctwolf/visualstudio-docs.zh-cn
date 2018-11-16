---
title: 报表挂钩函数 |Microsoft Docs
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
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3b7916f729f0d1ea1a254ecde8e5c53ea8b8a51
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51777249"
---
# <a name="report-hook-functions"></a>报表挂钩函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用安装的报表挂钩函数[_CrtSetReportHook](http://msdn.microsoft.com/library/1ae7c64f-8c84-4797-9574-b59f00f7a509)，每次调用[_CrtDbgReport](http://msdn.microsoft.com/library/6e581fb6-f7fb-4716-9432-f0145d639ecc)生成调试报告。 可以使用报告挂钩函数以及其他项筛选报告以集中于特定类型的分配。 报告挂钩函数应具有如下原型：  
  
```  
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 将指针传递给 **_CrtSetReportHook**属于类型 **_CRT_REPORT_HOOK**CRTDBG 中定义。H:  
  
```  
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 当运行库调用您的挂钩函数*nRptType*参数中包含的报表的类别 (**_CRT_WARN**， **_CRT_ERROR**，或 **_CRT_ASSERT**)， *szMsg*包含的全组装型的报告消息字符串、 指针和*retVal*指定是否`_CrtDbgReport`应继续正常执行后生成的报表或启动调试器。 (A *retVal*值为零继续执行，值为 1 启动调试器。)  
  
 如果挂钩完全处理了所涉及的消息，以便无报告要求，它应返回 **，则返回 TRUE**。 如果它返回**FALSE**，`_CrtDbgReport`通常情况下将报告消息。  
  
## <a name="see-also"></a>请参阅  
 [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 示例](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)



