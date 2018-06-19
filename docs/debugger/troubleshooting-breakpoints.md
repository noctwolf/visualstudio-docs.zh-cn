---
title: 在 Visual Studio 调试器的断点疑难解答 |Microsoft 文档
ms.custom: ''
ms.date: 01/23/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d587809a9690e312e923ba184c9d90c38405a5d6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31477100"
---
# <a name="troubleshoot-breakpoints-in-the-visual-studio-debugger"></a>在 Visual Studio 调试器的断点疑难解答

## <a name="breakpoint-warnings"></a>断点警告

断点在调试时，具有两个可能的可视状态： 一个实心的红色圆和 （白色填充） 空心圆。 如果调试器能够成功地在目标进程中设置断点，它会停留在一个实心的红色圆。 如果断点，空心圆断点处于禁用状态，或尝试将断点设置时出现警告。 若要确定的差别，将鼠标悬停在断点，并查看是否存在一条警告。

以下两节描述了突出显示的警告和如何解决它们。 

### <a name="no-symbols-have-been-loaded-for-this-document"></a>"无符号已加载此文档" 

转到**模块**窗口 (**调试** > **Windows** > **模块**) 并检查是否为你的模块加载。  
* 如果加载你的模块，请检查**符号状态**列以查看是否已加载符号。 
  * 如果未加载符号，请检查符号状态来诊断问题。 从上下文菜单中的模块上**模块**窗口中，单击**符号加载信息...** 若要查看调试器查找尝试并加载符号的位置。 有关加载符号的详细信息，请参阅[指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)。  
  * 如果已加载符号，这意味着 PDB 不包含有关你的源文件的信息。 以下是几个可能的原因： 
    * 如果最近已添加你的源文件，请确认正在加载的模块的最新版本。  
    * 可以创建使用去除的 Pdb **/PDBSTRIPPED**链接器选项。 已去除的 Pdb 不包含源文件信息。 确认你正在使用完整 PDB 和不去除的 PDB。  
    * PDB 文件部分已损坏。 请尝试删除文件并执行干净的生成的模块，若要查看如果此方法解决了问题。 

* 如果未加载你的模块，请检查以下内容来查找可能的原因： 
  * 确认你正在调试正确的进程。 
  * 若要查看你正在调试的代码的正确类型的检查。 你可以了解哪种类型的调试器配置为在调试的代码**进程**窗口 (**调试** > **Windows**  >  **进程**)。 如果你正在调试 C# 代码，例如，确认是否已你调试器配置为适当的.NET Framework 类型 (例如，托管 (v4\*) 而不是托管 (v2\*/v3\*) 而不是托管 (CoreCLR))。 

### <a name="-the-current-source-code-is-different-from-the-version-built-into"></a>"… 当前的源代码是内置于...的版本不同" 

如果源文件已更改，且源与正在调试的代码不再匹配，则调试器将不设置断点在代码中默认情况下。 通常情况下，更改一个源文件，但未重新生成的源代码时，将发生此问题。 若要解决此问题，重新生成项目。 如果生成系统认为该项目已经最新，即使它不是，你可以强制项目系统以重新生成通过再次保存源文件，或通过清除项目的生成之前生成的输出。 

在极少数情况下，你可能想要调试而不匹配的源代码。 这可以导致非常容易引起混淆的调试体验，因此请确保这是你想要继续。  

若要禁用这些安全检查，请执行以下操作： 
* 若要修改单个断点，将鼠标悬停在该断点图标在编辑器中，单击设置 （齿轮） 图标。 查看窗口添加到编辑器。 在查看窗口顶部是超链接，该值指示断点的位置。 单击超链接，以允许修改的断点位置，然后检查**允许源代码与原始版本不同**。
* 若要修改此设置的所有断点，请转到**调试** > **选项和设置**。 在 **“调试”/“常规”** 页上，清除 **“要求源文件与原始版本完全匹配”** 选项。 请确保要重新启用此选项，在完成时调试。 

## <a name="the-breakpoint-was-successfully-set-no-warning-but-didnt-hit"></a>断点已成功设置 （无警告），但未命中 

本部分提供信息来解决问题时调试器不显示任何警告 – 断点一个实心的红色圆时主动进行调试，尚不被命中断点。 

以下是需要检查的一些事项： 
1. 如果在多个进程或多台计算机中运行你的代码，请确保你正在调试的正确的进程或计算机。  
2. 确认你的代码正在运行。 一种简单测试这是添加对的调用`System.Diagnostics.Debugger.Break`（C# /vb/c + +） 或`__debugbreak`（c + +） 到在你尝试设置了断点，然后重新生成你的项目的代码行。 
3. 如果你正在调试优化的代码，请确保其中设置断点的函数不被内联到另一个函数。 `Debugger.Break`可工作的上一个检查中所述的测试来测试这一点也。 

## <a name="i-deleted-a-breakpoint-but-i-continue-to-hit-it-when-i-start-debugging-again"></a>我删除了断点，但在再次启动调试时继续命中该断点 

如果在调试时删除了断点，可能在下次开始调试的时再次命中该断点。 要停止命中此断点，请确保从 **“断点”** 窗口删除该断点的所有实例。  
