---
title: 错误： 无法自动单步执行服务器 |Microsoft Docs
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
- vs.debug.error.causality_no_server_response
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- remote debugging, notification error
ms.assetid: 9a370ccc-d358-429c-b285-9b6c0649bc68
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d75ed4ddb42705b95a5ddd834596bc828e0f3ec2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469262"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>错误：无法自动单步执行服务器
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[错误： 无法自动步骤到服务器](https://docs.microsoft.com/visualstudio/debugger/error-unable-to-automatically-step-into-the-server)。  
  
此错误显示如下：  
  
 无法自动单步执行服务器。 在远程过程执行前调试器未得到通知  
  
 当你尝试单步执行 Web 服务时，可能发生此错误（请参阅 [单步执行 XML Web services](http://msdn.microsoft.com/en-us/8e67de38-bf5f-41cc-a457-1b88ce63d764)）。 只要 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 未正确设置，就会发生此错误。  
  
 可能的原因有：  
  
-   Web.config 文件中的为你[!INCLUDE[vstecasp](../includes/vstecasp-md.md)]应用程序中未设置为"true"的调试 (请参阅[中的 ASP.NET 应用程序的调试模式](../debugger/how-to-enable-debugging-for-aspnet-applications.md))。  
  
-   版本的[!INCLUDE[vstecasp](../includes/vstecasp-md.md)]后安装 Visual Studio 安装了。 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 应在 Visual Studio 之前安装。 若要修复此问题，请使用 Window“控制面板” 和  “程序和功能”来修复 Visual Studio 安装。  
  
## <a name="see-also"></a>请参阅  
 [远程调试错误和故障排除](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [远程调试](../debugger/remote-debugging.md)



