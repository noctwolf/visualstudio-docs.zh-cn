---
title: 计算代码度量值
ms.date: 11/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code metrics [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b56db0d54e198e0d6d25b19db528ac979a3d44b4
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53056767"
---
# <a name="code-metrics-values"></a>代码度量值

现代软件应用程序的复杂性增加了使代码保持可靠、 可维护的难度也增加。 代码度量是一组软件度量值，使开发人员可以更好地了解他们正在开发的代码。 通过利用代码度量值，开发人员可以了解哪些类型和/或方法应该返工或更全面的测试。 开发团队可以确定潜在风险、 了解项目的当前状态并在软件开发过程中跟踪进度。

开发人员可以使用 Visual Studio 生成代码度量值数据中测量的复杂性和可维护性的托管代码。 可以为整个解决方案或单个项目生成代码度量数据。

有关如何在 Visual Studio 中生成代码度量数据的信息，请参阅[如何： 生成代码度量数据](../code-quality/how-to-generate-code-metrics-data.md)。

## <a name="software-measurements"></a>软件度量值

以下列表显示了代码 Visual Studio 计算的度量值结果：

- **可维护性指数**-计算表示相对轻松地维护代码的索引值介于 0 和 100 之间。 较高的值意味着更好的可维护性。 可以使用颜色编码，分级来快速确定在代码中的故障点。 绿色等级 20 到 100 之间，该值指示代码具有良好的可维护性。 黄色等级介于 10 到 19 之间，指示代码可维护性中等。 红色等级 0 到 9 之间的分级，表示可维护性低。

- **圈复杂度**-衡量代码的结构化的复杂程度。 通过计算该程序的流中的不同代码路径数则创建它。 具有复杂的控制流的程序将需要更多测试来实现良好的代码覆盖率并不容易维护。

- **继承深度**-指示扩展到类层次结构的根的类定义的数量。 越深的层次结构的难度可能会以了解其中定义特定的方法和字段或 / 和重新定义。

- **类耦合**-衡量与通过参数、 局部变量、 返回类型、 方法调用、 泛型或模板实例化、 基类，这些类、 接口实现、 外部类型上定义的字段的唯一类耦合程度和特性修饰。 类型和方法应具有高度内聚和较低的耦合，决定了优秀的软件设计。 高的耦合度表示设计，很难进行重复使用和维护由于其许多其他类型相互依赖关系。

- **代码行**-指示的代码中的行的大致数目。 计数为基础的 IL 代码，因此不精确的源代码文件中的行数。 计数过高可能表示类型或方法尝试执行的操作过多的工作，应进行拆分。 它还可能指示类型或方法可能很难维护。

   > [!NOTE]
   > [命令行版本](../code-quality/how-to-generate-code-metrics-data.md#command-line-code-metrics)代码的指标工具计算实际行代码，因为它分析而不是 IL 的源代码。

## <a name="anonymous-methods"></a>匿名方法

*匿名方法*就是没有名称的方法。 匿名方法最常用于将代码块作为委托参数传递。 度量值的匿名方法的声明在成员，如方法或访问器，结果与相关联的成员的声明的方法。 它们不会调用方法的成员与相关联。

代码度量值如何处理匿名方法的详细信息，请参阅[匿名方法和代码分析](../code-quality/anonymous-methods-and-code-analysis.md)。

## <a name="generated-code"></a>生成的代码

某些软件工具和编译器生成的代码的添加到项目和项目开发人员看不到或不应更改。 大多数情况下，代码度量值在计算度量值时忽略生成的代码。 这样，以反映开发人员可以查看和更改的指标值。

为 Windows 窗体生成的代码不忽略，因为它是开发人员可以查看和更改的代码。

## <a name="next-steps"></a>后续步骤

- [如何： 生成代码度量数据](../code-quality/how-to-generate-code-metrics-data.md)
- [使用代码度量结果窗口](../code-quality/working-with-code-metrics-data.md)