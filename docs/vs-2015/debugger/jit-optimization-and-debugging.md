---
title: JIT 优化和调试 |Microsoft Docs
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
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e798d44371f04b955db9019c741100ce9e5e5ef6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49201967"
---
# <a name="jit-optimization-and-debugging"></a>JIT 优化和调试
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

调试托管应用程序时[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]默认情况下取消优化实时 (JIT) 代码。 取消 JIT 优化意味着你调试的是非优化代码。 由于代码未优化，因此代码会运行得稍慢一些，但您的调试体验会更全面。 由于调试优化代码要更难一些，因此建议仅在遇到优化代码中发生的 bug 无法在非优化版本中重现时使用。  
  
 以控制 JIT 优化[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]由**在模块加载时取消 JIT 优化**选项。 您可以在找到此选项**常规**页**调试**中的节点**选项**对话框。  
  
 如果清除**在模块加载时取消 JIT 优化**选项，则可以调试优化的 JIT 代码，但调试的能力可能会受到限制，因为优化的代码与源代码不匹配。 因此，如调试器窗口**局部变量**并**自动**窗口可能无法显示尽可能多的信息就像调试非优化代码。  
  
 另一个重要差异是有关使用“仅我的代码”进行调试。 如果你正在使用“仅我的代码”进行调试，调试器就会将优化代码作为非用户代码处理，不在调试时显示。 因此，在调试 JIT 优化代码时，你可能想关闭“仅我的代码”。 有关详细信息，请参阅[限制为仅我的代码逐行调试](../debugger/just-my-code.md#BKMK_Enable_or_disable_Just_My_Code)。  
  
 请记住，**在模块加载时取消 JIT 优化**选项将模块加载时取消代码优化。 如果附加到已正在运行的进程，它可能包含已加载的代码、JIT 编译的代码和优化的代码。 **在模块加载时取消 JIT 优化**选项不起对这些代码，尽管它会影响在附加后加载的模块。 此外，**在模块加载时取消 JIT 优化**选项不影响用 NGEN 创建的模块，如 WinForms.dll。  
  
## <a name="see-also"></a>请参阅  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) （调试托管代码）  
 [Navigating through Code with the Debugger](../debugger/navigating-through-code-with-the-debugger.md) （使用调试器浏览代码）  
 [将附加到正在运行的进程](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [托管执行过程](http://msdn.microsoft.com/library/476b03dc-2b12-49a7-b067-41caeaa2f533)



