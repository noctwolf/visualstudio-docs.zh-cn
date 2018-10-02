---
title: 不支持对 IA64 进程执行混合模式调试。 | Microsoft Docs
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
- vs.debug.error.interop_unsupported_ia64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 20bc1e38-049b-4388-87c4-936815d85b46
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3777ce079aea853400896408542380c5e2d16ef5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476772"
---
# <a name="mixed-mode-debugging-for-ia64-processes-is-unsupported"></a>不支持对 IA64 进程执行混合模式调试。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[的 IA64 进程执行混合的模式调试不受支持。](https://docs.microsoft.com/visualstudio/debugger/mixed-mode-debugging-for-ia64-processes-is-unsupported)。  
  
Visual Studio 不支持对 IA64 进程中的托管代码和本机代码执行混合模式调试。 这意味着，当你进行调试时，无法从托管代码单步执行到本机代码，也无法从本机代码单步执行到托管代码。  
  
### <a name="workarounds"></a>问题解决  
  
-   在单独的调试会话中调试托管代码和本机代码。  
  
     - 或 -  
  
     作为 32 位进程调试混合代码，如下面的过程所述。  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>将平台更改为 32 位（Visual Basic 或 C#）  
  
1.  在中**解决方案资源管理器**，右键单击项目，然后单击**属性**的快捷菜单中。  
  
2.  在属性页中，单击**编译**或**调试**选项卡。  
  
3.  单击**平台**然后从平台列表中选择 x86。  
  
     默认情况下，Visual Basic 和 C# 编译器默认生成要在任何 CPU 上运行的代码。 在 64 位计算机上，这些二进制代码作为 64 位进程运行。 若要运行的 32 位进程，必须选择**Win32**，而非**AnyCPU**。  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>将平台更改为 32 位 (C/C++)  
  
1.  在中**解决方案资源管理器**，右键单击项目，然后单击**属性**的快捷菜单中。  
  
2.  在属性页中，单击**平台**，然后从平台列表中，选择 Win32  
  
## <a name="see-also"></a>请参阅  
 [调试 64 位应用程序](../debugger/debug-64-bit-applications.md)



