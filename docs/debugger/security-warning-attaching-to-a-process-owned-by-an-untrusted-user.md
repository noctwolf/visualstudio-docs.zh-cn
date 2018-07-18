---
title: 安全警告： 附加到不受信任的用户拥有的进程可能会十分危险。 如果以下信息查找可疑或您不确定，不附加到此进程 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.attachsecuritywarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68d88e01dde07789467272db830cae45ca5d60c4
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34178003"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>安全警告： 附加到不受信任的用户拥有的进程可能会十分危险。 如果以下信息查找可疑或您不确定，不附加到此进程
如果附加到包含部分可信代码或由不可信用户拥有的进程，则在该附加操作发生之前，会出现此警告对话框。 包含恶意代码的不可信进程可能会损害执行调试的计算机。 如果你有理由不信任该进程，则应单击**取消**阻止调试。  
  
 若要调试的合法方案时，禁止显示此警告，关闭 Visual Studio 中，并将此注册表项的值设置为 1: `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning`，然后重新启动 Visual Studio。 在调试完方案后，请将值重置为 0，并重新启动 Visual Studio。  
  
 “可信用户”包括您自己以及一组标准用户，通常在安装有 .NET Framework 的计算机上定义了这些用户（如 `aspnet`、`localsystem`、`networkservice` 和 `localservice`）。  
  
## <a name="uielement-list"></a>UIElement 列表  
 名称  
 为调试而请求的程序集的名称  
  
 “用户”  
 当前用户  
  
 Attach  
 按下它即可通过附加来继续进行调试  
  
 不附加  
 不附加到进程  
  
## <a name="see-also"></a>请参阅  
 [将附加到正在运行的进程](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [调试器安全](../debugger/debugger-security.md)