---
title: "JIT 优化和调试 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 23de1ec4e053a87c4f91cf7b599f49b8fe318015
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="jit-optimization-and-debugging"></a>JIT 优化和调试
**优化.NET 中的工作原理：**如果你尝试调试代码，它更容易。 当将该代码是否为**不**优化。 这是因为当代码进行了优化，编译器和运行时对代码进行更改发出 CPU，以便它运行速度更快，但具有到原始源代码的间接映射。 也就是说，调试器会经常无法告诉你的本地变量的值和代码单步执行，断点可能无法按预期工作。

通常发布生成配置创建优化的代码并调试生成配置不。 `Optimize` MSBuild 属性控制是否被告知编译器优化代码。

.NET 生态系统中, 打开的代码是从源到 CPU 两步骤过程中的说明进行操作： 首先，C# 编译器将你键入的文本转换为调用 MSIL 的中间二进制形式并将此写出到.dll 文件。 更高版本，.NET 运行时将此 MSIL 转换为 CPU 说明。 这两个步骤可以优化在某种程度上，但由.NET 运行时执行的第二步执行的更重要的优化。

**在模块加载 （仅限托管） 时取消 JIT 优化选项：**调试器将显示一个选项，用于控制在目标进程内部的使用启用优化进行编译的 DLL 加载时，会发生什么情况。 如果未选中此选项 （默认状态），则当.NET 运行时编译到 CPU 的代码的 MSIL 代码，则会使启用优化。 如果选中此选项，调试器请求禁用优化。

**在模块加载 （仅限托管） 时取消 JIT 优化**上找不到选项**常规**下页上**调试**中的节点**选项**对话框。

**当应选中此选项：**选中此选项，当从另一个源，如 nuget 包，下载 Dll，并且你想要调试此 DLL 中的代码。 为了使这种方式，还必须针对此 DLL 中找到的符号 (.pdb) 文件。

如果只想调试本地生成的代码，则最好选中此选项，因为在某些情况下，启用此选项将会显著降低调试。 有两个原因减慢：

* 优化的代码运行速度更快。 如果你关闭了大量代码优化，可以添加对性能的影响。
* 如果必须启用仅我的代码，则调试器将甚至不尝试并加载符号的进行了优化的 Dll。 查找符号可能需要很长时间。

**此选项的限制：**有两种情况下，此选项会将其中**不**工作：

1. 在将调试器附加到已运行的进程的其中的情况下，此选项将产生在已附加调试器时已经加载的模块上的任何影响。
2. 此选项不起 Dll 已预编译为本机代码 (即 ngen'ed)。 但是，你可以通过与环境变量 COMPlus_ZapDisable 设置为 '1' 中启动该进程禁用预编译的代码的使用情况。

## <a name="see-also"></a>请参阅  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) （调试托管代码）  
 [Navigating through Code with the Debugger](../debugger/navigating-through-code-with-the-debugger.md) （使用调试器浏览代码）  
 [将附加到正在运行的进程](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [托管执行过程](/dotnet/standard/managed-execution-process)
