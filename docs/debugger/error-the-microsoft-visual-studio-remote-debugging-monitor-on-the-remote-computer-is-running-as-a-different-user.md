---
title: 错误：远程计算机上的 Microsoft Visual Studio 远程调试监视器正在以其他用户身份运行
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1cb477cf852d0e07bf14f344b3dc27b20a56de59
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53067728"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>错误：远程计算机上的 Microsoft Visual Studio 远程调试监视器正在以其他用户身份运行
当尝试执行远程调试时，您可能会收到如下错误信息：  
  
 远程计算机上的“Microsoft Visual Studio 远程调试监视器”正在以其他用户身份运行。  
  
## <a name="cause"></a>原因  
 当您正在“无身份验证”模式下进行调试，而启动 msvsmon 的用户不是运行 Visual Studio 的用户时，会出现此消息。  
  
## <a name="solution"></a>解决方案  
 最安全也是最好的解决方案是，以与运行 Visual Studio 的相同用户帐户运行远程调试监视器 (msvsmon.exe)。 如果无法做到这一点，则可以在远程调试监视器的“选项”对话框中选中“允许任何用户进行调试”选项，使用其他用户帐户运行远程调试监视器。  
  
> [!CAUTION]
>  授予其他用户进行连接的权限可能会导致意外地连接到错误的远程调试会话。 以“无身份验证”模式进行调试从来都不是安全的，应该谨慎使用。
  
## <a name="see-also"></a>请参阅  
 [远程调试错误和疑难解答](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)