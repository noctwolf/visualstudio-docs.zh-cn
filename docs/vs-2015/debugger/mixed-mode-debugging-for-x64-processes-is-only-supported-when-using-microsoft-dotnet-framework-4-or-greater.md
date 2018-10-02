---
title: 混合的模式调试支持对 x64 进程是仅当使用 microsoft.net Framework 4 或更高版本 |Microsoft Docs
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
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0297d9bcfb380261d2ad2e73853ded70285f1b35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471681"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>仅当使用 Microsoft .NET Framework 4 或更高版本时，才支持对 x64 进程进行混合模式调试
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[混合的模式调试支持对 x64 进程是仅当使用 microsoft.net Framework 4 或更高版本](https://docs.microsoft.com/visualstudio/debugger/mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoft-dotnet-framework-4-or-greater)。  
  
NET Framework 版本之前 4 不提供支持混合模式调试的 x64 的处理。 这意味着，当你进行调试时，无法从托管代码单步执行到本机代码，也无法从本机代码单步执行到托管代码。  
  
### <a name="workarounds"></a>问题解决  
  
-   更新项目，使其使用 Microsoft .NET Framework 4 或更高版本。  
  
     - 或 -  
  
     在单独的调试会话中调试托管代码和本机代码。  
  
     - 或 -  
  
     作为 32 位进程调试混合代码，如下面的过程所述。  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>将平台更改为 32 位（Visual Basic 或 C#）  
  
1.  在中**解决方案资源管理器**，右键单击你的项目，然后单击**属性**。  
  
2.  在属性页中，单击**编译**或**调试**选项卡。  
  
3.  单击**平台**然后从平台列表中选择 x86。  
  
     默认情况下，Visual Basic 和 C# 编译器默认生成要在任何 CPU 上运行的代码。 在 64 位计算机上，这些二进制代码作为 64 位进程运行。 若要运行的 32 位进程，必须选择**Win32**，而非**AnyCPU**。  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>将平台更改为 32 位 (C/C++)  
  
1.  在中**解决方案资源管理器**，右键单击项目，然后单击**属性**。  
  
2.  在属性页中，单击**平台**然后从平台列表中选择 Win32。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   请参阅[设置 SQL 调试](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)。  
  
## <a name="see-also"></a>请参阅  
 [调试 64 位应用程序](../debugger/debug-64-bit-applications.md)



