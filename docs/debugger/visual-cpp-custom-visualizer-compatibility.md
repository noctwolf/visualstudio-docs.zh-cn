---
title: Visual C/c + + 自定义可视化工具兼容性
ms.date: 01/28/2019
ms.prod: visual-studio-dev16
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging assertions
- assertions, debugging
- assertions, assertion failures
- Assertion Failed dialog box
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.openlocfilehash: 32e38dd3bba8a1127d8756972b73e8b47a514f1b
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335176"
---
# <a name="visual-cc-custom-visualizer-compatibility"></a>Visual C/c + + 自定义可视化工具兼容性

从 Visual Studio 2019，Visual c + + 包括使用外部的 64 位进程来托管其占用大量内存的组件使用改进的调试器。 作为此更新的一部分，必须更新到 Visual C/c + + 表达式计算器某些扩展，使它们与新的调试器兼容。

如果您当前正在使用旧的 C/c + + EE 外接程序或 C/c + + 自定义可视化工具，您可以通过转到将关闭此外部过程的使用情况**工具** > **选项** >  **调试**，再取消选中**加载调试符号在外部进程 （仅限本机） 中**。 如果取消选择此选项，将出现在 IDE (devenv.exe) 进程内的内存使用率显著增加。 因此，如果想要调试大型项目，则建议使用扩展的所有者，以使其与此调试选项兼容。

如果你是旧的 C/c + + EE 外接程序或 C/c + + 自定义可视化工具的所有者，可以找到有关选择加入上加载你的工作进程中的扩展详细信息[Concord 扩展性示例 wiki](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Worker-Process-Remoting)。 此外可以找到[C/c + + 自定义可视化工具示例](https://github.com/Microsoft/ConcordExtensibilitySamples/tree/master/CppCustomVisualizer)。