---
title: 如何： 调试 ASP.NET 异常 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], ASP.NET exceptions
- ASP.NET, exceptions
- exceptions, ASP.NET
ms.assetid: 1810096e-de8c-435e-be3d-f365d0cd0a6a
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d505e67018c24f659e88401b565011a4c7bea96
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51789208"
---
# <a name="how-to-debug-aspnet-exceptions"></a>如何：调试 ASP.NET 异常
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

调试异常是开发可靠的一个重要部分[!INCLUDE[vstecasp](../includes/vstecasp-md.md)]应用程序。 有关如何调试异常的常规信息位于[管理调试器的异常](../debugger/managing-exceptions-with-the-debugger.md)。  
  
 若要调试未处理的[!INCLUDE[vstecasp](../includes/vstecasp-md.md)]异常，您必须确保调试器停止为它们。 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 运行时有一个顶级异常处理程序。 因此，默认情况下，调试器绝不会在未经处理的异常中中断。 若要引发异常时中断调试器，必须选择**发生异常时中断： 引发**设置为在该特定异常**异常**对话框。  
  
 如果已启用仅我的代码，**发生异常时中断： 引发**不会导致调试器立即中断，如果在.NET Framework 方法或其他系统代码中引发异常。 执行将继续，直至调试器命中非系统代码时才中断。 因此，不必在发生异常时逐句通过系统代码。  
  
 仅我的代码提供了可以变得更为有用的另一个选项：**发生异常时中断： 用户未处理**。 如果为异常选择此设置，则调试器将在用户代码中中断执行，但是仅当异常没有被用户代码捕获和处理时，它才这样做。 此设置会使顶级 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 异常处理程序不起作用，因为该处理程序位于非用户代码中。  
  
### <a name="to-enable-debugging-of-aspnet-exceptions-with-just-my-code"></a>启用 ASP.NET 异常调试和“仅我的代码”  
  
1.  上**调试**菜单上，单击**异常**。  
  
     **异常**对话框随即出现。  
  
2.  上**公共语言运行时异常**行中，选中**引发**或**用户未处理**。  
  
     若要使用**未经用户处理**设置，**仅我的代码**必须启用...  
  
### <a name="to-use-best-practices-for-aspnet-exception-handling"></a>采用 ASP.NET 异常处理的最佳做法  
  
-   在可能引发你知道如何处理的可预见异常的代码周围放置 `try … catch` 块。 例如，如果应用程序正在调用到 XML Web 服务或直接向 SQL Server，该代码应为在**try...catch**块中，因为可能出现的大量异常。



