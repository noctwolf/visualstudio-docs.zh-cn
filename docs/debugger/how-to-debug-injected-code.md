---
title: 如何： 调试插入的代码 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.injected
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- assembly language, viewing
- debugging [C++], viewing assembly code
- debugging [C++], injected code
- debugging [C++], enabling source annotation
- injected code
- Show Source Code command [debugger]
- debugging [C++], using attributes
- disassembly code, debugging
ms.assetid: a1b4104d-d49e-451f-a91e-e39ceaf35875
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 479df9e5761066248b8657d9656132b072bddb13
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49866072"
---
# <a name="how-to-debug-injected-code"></a>如何：调试插入的代码
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在“工具”菜单上选择“导入和导出设置”。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)。  
  
 使用特性可大大简化 C++ 编程。 有关详细信息，请参阅[概念](/cpp/windows/attributed-programming-concepts)。 某些特性由编译器直接解释。 其他特性则向程序源中插入代码，然后由编译器进行编译。 此类插入的代码通过减少你必须编写的代码量使编程变得更容易。 但有时 bug 可能导致应用程序在执行插入的代码时失败。 发生这种情况时，你可能希望查看插入的代码。 Visual Studio 提供两种查看插入的代码的方法：  
  
- 您可以查看中插入的代码**反汇编**窗口。  
  
- 使用[/Fx](/cpp/build/reference/fx-merge-injected-code)，可以创建合并的源文件，其中包含原始和注入的代码。  
  
  **反汇编**窗口会显示对应的源代码和特性所插入的代码的程序集语言说明。 此外，**反汇编**窗口可以显示源代码批注。  
  
### <a name="to-turn-on-source-annotation"></a>打开源批注  
  
-   右键单击**反汇编**窗口中，选择**显示源代码**从快捷菜单。  
  
     如果您知道在源窗口中特性的位置，可以使用快捷菜单来查找中插入的代码**反汇编**窗口。  
  
### <a name="to-view-injected-code"></a>查看插入的代码  
  
1.  调试器必须处于中断模式。  
  
2.  在源代码窗口中，将光标放在要查看其插入代码的特性前面。  
  
3.  右键单击，然后选择**转到反汇编**从快捷菜单。  
  
     如果特性位置是当前执行点附近，则可以选择**反汇编**从窗口**调试**菜单。  
  
### <a name="to-view-the-disassembly-code-at-the-current-execution-point"></a>查看当前执行点处的反汇编代码  
  
1.  调试器必须处于中断模式。  
  
2.  从**调试**菜单中，选择**Windows**，然后单击**反汇编**。  
  
## <a name="see-also"></a>请参阅  
 [调试器安全](../debugger/debugger-security.md)   
 [调试本机代码](../debugger/debugging-native-code.md)