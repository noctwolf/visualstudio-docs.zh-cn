---
title: 安全警告：附加到不受信任的用户所拥有的进程可能很危险。 以下信息看上去可疑或者你不确定，如果未附加到此进程 |Microsoft Docs
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
- vs.debug.attachsecuritywarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b856ac3a61d8af72d78546948bbe4ab780e9512e
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "47588595"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>安全警告：附加到不受信任的用户所拥有的进程可能很危险。 如果以下信息看上去可疑或者你无法确定，请勿附加到此进程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[安全警告： 附加到不受信任的用户所拥有的进程可能很危险。以下信息看上去可疑或者你不确定，如果未附加到此进程](https://docs.microsoft.com/visualstudio/debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process)。  
  
如果附加到包含部分可信代码或由不可信用户拥有的进程，则在该附加操作发生之前，会出现此警告对话框。 包含恶意代码的不可信进程可能会损害执行调试的计算机。 如果您有理由不信任该进程，则应单击**取消**阻止调试。  
  
 若要调试合法方案时，禁止显示此警告，请关闭 Visual Studio 中，并将此注册表项的值设置为 1: `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning`，然后重新启动 Visual Studio。 在调试完方案后，请将值重置为 0，并重新启动 Visual Studio。  
  
 “可信用户”包括您自己以及一组标准用户，通常在安装有 .NET Framework 的计算机上定义了这些用户（如 `aspnet`、`localsystem`、`networkservice` 和 `localservice`）。  
  
## <a name="uielement-list"></a>UIElement 列表  
 name  
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



