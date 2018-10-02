---
title: 如何： 使用调用堆栈窗口 |Microsoft Docs
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
- vs.debug.callstack
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- SQL
- aspx
helpviewer_keywords:
- threading [Visual Studio], displaying calls to or from
- functions [debugger], viewing code on call stack
- disassembly code
- breakpoints, Call Stack window
- debugging [Visual Studio], switching to another stack frame
- debugging [Visual Studio], Call Stack window
- Call Stack window, viewing source code for functions on the call stack
- stack, switching stack frames
- Call Stack window, viewing disassembly code for functions on the call stack
ms.assetid: 5154a2a1-4729-4dbb-b675-db611a72a731
caps.latest.revision: 45
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75b617e9de62c20cc1e8a32cf993f5f03201f4fc
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "47588706"
---
# <a name="how-to-use-the-call-stack-window"></a>如何：使用“调用堆栈”窗口
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[在 Visual Studio 调试器中查看调用堆栈](https://docs.microsoft.com/visualstudio/debugger/how-to-use-the-call-stack-window)。  
  
通过使用**调用堆栈**窗口中，可以查看当前是在堆栈的函数或过程调用。  
  
 **调用堆栈**窗口中显示的每个函数和编程语言中编写的名称。 函数或过程名称可能包含可选信息，如模块名称、行号、参数名称、类型和值。 可以打开或关闭这些可选信息的显示。  
  
 一个黄色箭头标识执行指针当前所位于的堆栈帧。 默认情况下，这是在源中，将显示其信息的帧**反汇编**，**局部变量**，**监视**，以及**自动**windows。 如果你想要将上下文更改为堆栈上的另一个帧，可以执行的操作**调用堆栈**窗口。  
  
 当调试符号不可用的一部分调用堆栈时**调用堆栈**窗口可能不能显示那部分调用堆栈的正确信息。 将出现以下表示法：  
  
 [下面的帧可能不正确和/或缺失，没有为 name.dll 加载符号]  
  
 在托管代码中，默认情况下。 **调用堆栈**窗口将隐藏非用户代码的信息。 在隐藏信息处出现以下表示法：  
  
 **[\<外部代码 >]**  
  
 非用户代码是任何代码，这些代码不是可通过快捷菜单选择以显示非用户代码的调用堆栈信息的我的代码。  
  
 可以使用快捷菜单选择查看线程之间的调用。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你的当前设置或版本。 若要更改设置，请选择**导入和导出设置**上**工具**菜单。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-display-the-call-stack-window-in-break-mode-or-in-run-mode"></a>以中断模式或运行模式显示“调用堆栈”窗口  
  
-   上**调试**菜单中，选择**Windows** ，然后单击**调用堆栈**。  
  
### <a name="to-change-the-optional-information-displayed"></a>更改显示的可选信息  
  
-   右键单击**调用堆栈**窗口和设置或清除**显示\<** _所需的信息_**>**.  
  
### <a name="to-display-non-user-code-frames-in-the-call-stack-window"></a>在“调用堆栈”窗口中显示非用户代码帧  
  
-   右键单击**调用堆栈**窗口，然后选择**显示外部代码**。  
  
### <a name="to-switch-to-another-stack-frame"></a>切换到另一个堆栈帧  
  
1.  在中**调用堆栈**窗口中，右键单击该帧其代码和您想要查看的数据。  
  
2.  选择**切换到帧**。  
  
     一个带有卷尾的绿色箭头显示在所选帧旁。 执行指针保留在原始帧中，仍然用黄色箭头标记。 如果选择**步骤**或**继续**从**调试**菜单中，执行将继续在原始帧中，选择不是框架。  
  
### <a name="to-display-calls-to-or-from-another-thread"></a>显示与其他线程之间的来回调用  
  
-   右键单击**调用堆栈**窗口，然后选择**包括对其他线程和来自其他线程的调用**。  
  
### <a name="to-view-the-source-code-for-a-function-on-the-call-stack"></a>查看调用堆栈上的函数的源代码  
  
-   在中**调用堆栈**窗口中，右键单击要查看，并选择其源代码的函数**转到源代码**。  
  
### <a name="to-visually-trace-the-call-stack"></a>直观地跟踪调用堆栈  
  
1.  在中**调用堆栈**窗口中，打开快捷菜单。 选择**在代码图上显示调用堆栈**。 (键盘： **CTRL** + **SHIFT** + **`**)  
  
     请参阅[调试时映射调用堆栈上的方法](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)。  
  
### <a name="to-view-the-disassembly-code-for-a-function-on-the-call-stack"></a>查看调用堆栈上的函数的反汇编代码  
  
-   在中**调用堆栈**窗口中，右键单击要查看，并选择其反汇编代码的函数**转到反汇编**。  
  
### <a name="to-run-to-a-specific-function-from-the-call-stack-window"></a>从“调用堆栈”窗口运行到特定函数  
  
-  在中**调用堆栈**窗口中，选择函数，右键单击并选择**运行到光标处**。  
  
### <a name="to-set-a-breakpoint-on-the-exit-point-of-a-function-call"></a>在函数调用的退出点上设置断点  
  
-   请参阅[的调用堆栈函数处设置断点](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_in_the_call_stack_window)。  
  
### <a name="to-load-symbols-for-a-module"></a>加载模块符号  
  
-   在中**调用堆栈**窗口中，右键单击显示该模块的符号的帧，你想要重新加载，然后选择**加载符号**。  
  
## <a name="loading-symbols"></a>加载符号  
 在中**调用堆栈**窗口中，您可以加载调试符号的当前没有加载的符号的代码。 这些符号可以是从 Microsoft 公共符号服务器下载的 .NET Framework 符号或系统符号，也可以是正在调试的计算机上的某个符号路径中的符号。  
  
 请参阅[指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols"></a>加载符号  
  
1.  在中**调用堆栈**窗口中，右键单击未加载符号的帧。 此帧将显示为灰色。  
  
2.  指向**负载从符号**，然后单击**Microsoft 符号服务器**或**符号路径**。  
  
#### <a name="to-set-the-symbol-path"></a>设置符号路径  
  
1.  在中**调用堆栈**窗口中，选择**符号设置**从快捷菜单。  
  
     **选项**对话框将打开并**符号**显示页。  
  
2.  单击**符号设置**。  
  
3.  在中**选项**对话框框中，单击文件夹图标。  
  
     在中**符号文件 (.pdb) 位置**框中，将出现一个光标。  
  
4.  键入所调试的计算机上的符号位置的目录路径名。 对于本地调试，此计算机指您的本地计算机。 对于远程调试，此计算机指远程计算机。  
  
5.  单击“确定”关闭“选项”对话框 。  
  
## <a name="see-also"></a>请参阅  
 [混合的代码与调用堆栈窗口中缺少的信息](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md)   
 [如何： 更改调试器 Windows 的数字格式](http://msdn.microsoft.com/library/cd593847-a625-411d-a430-b798346ef18f)   
 [查看调试器中的数据](../debugger/viewing-data-in-the-debugger.md)   
 [指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [使用断点](../debugger/using-breakpoints.md)





