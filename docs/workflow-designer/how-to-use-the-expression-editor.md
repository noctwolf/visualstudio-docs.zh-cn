---
title: 工作流设计器-如何： 使用表达式编辑器
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Presentation.View.ExpressionTextBox.UI
ms.assetid: b5f961dd-6dda-41a9-9cae-0383d479ef3d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1f2ab9cad6f54b8d1106fd68eb017434cf5cfef
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756137"
---
# <a name="how-to-use-the-expression-editor"></a>如何：使用表达式编辑器

表达式编辑器是在多个工作流活动中使用输入并计算表达式的工作流设计器控件。 表达式编辑器提供了完备的 IDE 编辑体验，包括 IntelliSense、 着色、 ParamInfo、 错误波形曲线和其他功能。 编译器在表达式后验证其输入。 如果表达式无效，则显示一个错误图标。 此外可以为打开编辑器**表达式编辑器**对话框。

表达式是绑定到参数或属性的文本值或 Visual Basic 代码。 它们包含与操作以生成新值进行组合的值元素 （例如，变量、 常量、 文本、 属性）。 表达式使用 VB.NET 语法编写，即使应用程序使用 C# 编程也如此。 这意味着，大小写并不重要，则执行比较，使用单个等登录 （"="而不是"= ="），布尔运算符是单词"和"和"而不是符号"& &"和"| |"，并**执行任何操作**使用而不是**null**。 表达式和运算符在 Visual Basic 中的详细信息以及一些示例，请参阅[运算符和表达式在 Visual Basic 中的](/previous-versions/visualstudio/visual-studio-2010/a1w3te48(v=vs.100))。

**表达式编辑器**行为，如下所示：

- 当焦点不在表达式编辑器上时，该编辑器看上去像一个常规 TextBlock 控件。

- 当焦点在表达式编辑器上时，该编辑器的外观和行为都类似于表达式编辑器控件。 失去焦点后，表达式编辑器看上去像一个常规 TextBlock 试。

- 如果在重新承载的工作流设计器中将焦点置于表达式编辑器，则该编辑器的行为类似于 TextBox。 当在重新承载的工作流设计器中失去焦点后，表达式编辑器看上去又像一个常规 TextBlock 了。

> [!NOTE]
> 仅在 Visual Studio 中提供表达式编辑器的 IntelliSense。 在 Visual Studio 和重新承载的方案中，编译器对表达式进行验证后它会输入，并且如果表达式无效，表达式编辑器将显示一个错误图标。

## <a name="use-the-expression-editor"></a>使用表达式编辑器

1.  在 Visual Studio 中，打开一个新的或现有的工作流项目。

2.  向工作流添加诸如 <xref:System.Activities.Statements.Assign> 之类的活动。

    > [!NOTE]
    > 多种工作流活动具有表达式编辑器。 表达式 TextBlock 还显示在变量设计器、参数设计器和动态参数设计器中。 <xref:System.Activities.Statements.Assign> 活动用作一个示例。

3.  在 <xref:System.Activities.Statements.Assign> 活动的活动设计器中单击左侧表达式编辑器。

     灰色水印字符串**\<到 >** 并**\<输入 VB 表达式 >** 是默认文本字符串中的表达式编辑器<xref:System.Activities.Statements.Assign>活动。

4.  输入表达式。 如果您输入一个字符串，请确保在该字符串两端加上引号。 如果你选择将表达式自变量绑定到一个变量，请不要使用引号。

     完成后，选择区域或区域外部表达式编辑器来将焦点移到设计器的另一个部分。 转移焦点会导致编译器以验证该表达式，如前面所述。

     输入或编辑表达式的替代方法是单击属性网格中的属性名称旁边的省略号。 选择省略号将打开**表达式编辑器**作为对话框。

## <a name="see-also"></a>请参阅

- <xref:System.Activities.Presentation.View.ExpressionTextBox>