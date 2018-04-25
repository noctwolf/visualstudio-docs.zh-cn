---
title: 快速操作 | Microsoft Docs
ms.date: 03/28/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 941980eff8fc2474df9555b326278abdb9b26dac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="quick-actions"></a>快速操作

通过快速操作，只凭单个操作便可轻松重构、生成或修改代码。 快速操作可用于 C#、[C++](/cpp/ide/writing-and-refactoring-code-cpp) 和 Visual Basic 代码文件。 某些操作特定于一种语言，而其他操作适用于所有语言。

可使用“快速操作”功能：

- 使用代码修补程序处理[代码分析器](../code-quality/roslyn-analyzers-overview.md)规则冲突的问题
- [取消显示](../code-quality/use-roslyn-analyzers.md)代码分析器规则冲突
- 应用重构（例如[内联临时变量](../ide/reference/inline-temporary-variable.md)）
- 生成代码（例如[引入局部变量](../ide/reference/introduce-local-variable.md)）

可使用灯泡图标![小灯泡图标](media/vs2015_lightbulbsmall.png)或按“Ctrl”+**应用快速操作。** 当光标位于可操作的代码行上时， 如果有红色波形曲线，则将看到灯泡，Visual Studio 针对如何解决此问题有一条建议。 例如，如果你遇到红色波形曲线指示的错误，则在可对该错误进行修复时，会显示灯泡。

第三方可针对任何语言提供自定义诊断和建议，例如随附 SDK 提供，同时根据这些规则，Visual Studio 电灯泡可能亮起。

## <a name="to-see-a-light-bulb"></a>查看电灯泡

1. 在很多情况下，当光标指针悬停在错误点上方时自然显示电灯泡，或者当你在将插入点移动到存在错误的行中时，编辑器左边距处自然显示电灯泡。 看到红色波形曲线时，可悬停在其上方，以显示电灯泡。 使用鼠标或键盘转到问题发生的行时，也会显示电灯泡。

1. 按“Ctrl”+**。** 可调用电灯泡并直接转到潜在修复列表。

   ![带鼠标悬停的灯泡](../ide/media/vs2015_lightbulb_hover.png)

## <a name="to-see-potential-fixes"></a>查看潜在修复

单击向下箭头或“显示潜在修复”链接，以显示电灯泡可执行的快速操作列表。

![灯泡已展开](../ide/media/vs2015_lightbulb_hover_expanded.png)

## <a name="see-also"></a>请参阅

- [Visual Studio 中的代码生成](../ide/code-generation-in-visual-studio.md)
- [常见快速操作](../ide/common-quick-actions.md)
- [代码样式和快速操作](../ide/code-styles-and-quick-actions.md)
- [编写和重构代码 (C++)](/cpp/ide/writing-and-refactoring-code-cpp)