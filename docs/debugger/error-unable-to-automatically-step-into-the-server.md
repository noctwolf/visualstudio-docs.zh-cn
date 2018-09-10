---
title: 错误： 无法自动单步执行服务器 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, notification error
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b9e7b3c45e49425c07c545f2a04673887fc8cac7
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44278668"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>错误：无法自动单步执行服务器
此错误显示如下：  
  
 无法自动单步执行服务器。 在远程过程执行前调试器未得到通知  
  
 当你尝试单步执行 web 服务时，会出现此错误 (请参阅[单步执行到 XML Web 服务](https://msdn.microsoft.com/library/8e67de38-bf5f-41cc-a457-1b88ce63d764))。 只要 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 未正确设置，就会发生此错误。  
  
 可能的原因有：  
  
-   [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 应用程序的 web.config 文件未将调试设置为“true”（请参见 [ASP.NET 应用程序中的调试模式](../debugger/how-to-enable-debugging-for-aspnet-applications.md)）。  
  
-   在安装 Visual Studio 后安装了某个版本的 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 。 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 应在安装 Visual Studio 之前安装。 若要解决此问题，请使用 Windows**控制面板 > 程序和功能**来修复 Visual Studio 安装。  
  
## <a name="see-also"></a>请参阅  
 [远程调试错误和故障排除](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [远程调试](../debugger/remote-debugging.md)