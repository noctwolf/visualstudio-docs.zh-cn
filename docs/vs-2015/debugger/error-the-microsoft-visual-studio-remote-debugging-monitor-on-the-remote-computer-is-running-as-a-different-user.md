---
title: 错误： Microsoft Visual Studio 远程调试监视器在远程计算机上以不同用户身份运行 |Microsoft Docs
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
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
ms.assetid: e5b18734-2daf-4c58-b5de-24ae1295703e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba0c145f94e0d4213cdc859edb3b43710d96d257
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205746"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>错误：远程计算机上的 Microsoft Visual Studio 远程调试监视器正以其他用户身份运行
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

当尝试执行远程调试时，您可能会收到如下错误信息：  
  
 远程计算机上的“Microsoft Visual Studio 远程调试监视器”正在以其他用户身份运行。  
  
## <a name="cause"></a>原因  
 当您正在“无身份验证”模式下进行调试，而启动 msvsmon 的用户不是运行 Visual Studio 的用户时，会出现此消息。  
  
## <a name="solution"></a>解决方案  
 最安全也是最好的解决方案是，以与运行 Visual Studio 的相同用户帐户运行远程调试监视器 (msvsmon.exe)。 如果无法做到这一点，您可以使用其他帐户下运行远程调试监视器**允许任何用户进行调试**选项处于选中状态中远程调试监视器**选项**对话框。  
  
> [!CAUTION]
>  授予其他用户进行连接的权限可能会导致意外地连接到错误的远程调试会话。 在中进行调试**无身份验证**模式不安全，应谨慎使用。  
  
 有关详细信息，请参阅[启动远程调试监视器](http://msdn.microsoft.com/library/55b60ce7-834b-4e83-a10e-fe4248260a4c)。  
  
## <a name="see-also"></a>请参阅  
 [远程调试错误和故障排除](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)



