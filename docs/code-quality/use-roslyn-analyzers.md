---
title: 使用以及在 Visual Studio 配置 Roslyn 分析器
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2e99a98f5ea4cca5891d416bdc13656b3173a40f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31925115"
---
# <a name="configure-and-use-roslyn-analyzer-rules"></a>配置和使用 Roslyn 分析程序规则

.NET compiler Platform ("Roslyn") 分析程序规则，或*诊断*，分析你的 C# 或 Visual Basic 代码，你进行键入。 每个诊断已为你的项目时可以覆盖默认严重性和抑制状态。 本文介绍如何设置规则严重性，使用规则集，并禁止显示冲突。

## <a name="analyzers-in-solution-explorer"></a>在解决方案资源管理器的分析器

你可以执行自定义从分析器诊断大量**解决方案资源管理器**。 如果你[安装分析器](../code-quality/install-roslyn-analyzers.md)作为 NuGet 程序包，**分析器**节点显示在**引用**或**依赖关系**中的节点**解决方案资源管理器**。 如果你展开**分析器**，以及然后展开某个分析器的程序集，请参阅在程序集中的所有诊断。

![在解决方案资源管理器的分析器节点](media/analyzers-expanded-in-solution-explorer.png)

你可以查看的诊断，包括其描述和默认严重性中的属性**属性**窗口。 若要查看属性，请右键单击该规则并选择**属性**，或选择规则，然后按**Alt**+**Enter**。

![在属性窗口中的诊断属性](media/analyzer-diagnostic-properties.png)

若要查看的诊断的联机文档，请右键单击诊断程序，然后选择**视图帮助**。

中的每个诊断旁边的图标**解决方案资源管理器**对应于你的规则集中当在编辑器中打开它时可以看到的图标：

- 圆圈，圆圈中的"i"指示[严重性](#rule-severity)的**信息**
- "！"三角形，三角形中指示[严重性](#rule-severity)的**警告**
- 圆圈，圆圈中的"x"指示[严重性](#rule-severity)的**错误**
- 浅色背景圆圈，圆圈中的"i"指示[严重性](#rule-severity)的**Hidden**
- 圆圈，圆圈中的向下箭头指示禁止显示该诊断

![在解决方案资源管理器的诊断图标](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-sets"></a>规则集

A[规则集](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)是存储单个诊断的严重性和抑制状态的 XML 文件。 规则集应用于单个项目，并且项目可以具有多个规则集。 若要查看活动规则集编辑器中，右键单击**分析器**中的节点**解决方案资源管理器**和选择**打开活动规则集**。 如果这是首次访问规则设置，名为的文件 *\<projectname >.ruleset*添加到项目，并出现在**解决方案资源管理器**。

> [!NOTE]
> 规则集包括静态 （二进制） 的代码分析和 Roslyn 分析器规则。

你可以更改为一个项目中的设置活动规则**代码分析**项目的属性选项卡。 选择中的规则集**运行此规则集**下拉列表。 你也可以打开的规则集从**代码分析**属性页上通过选择**打开**。

## <a name="rule-severity"></a>规则严重性

你可以配置的分析程序规则的严重性或*诊断*，如果你[安装分析器](../code-quality/install-roslyn-analyzers.md)作为 NuGet 程序包。 下表显示诊断的严重性选项：

|严重性|生成时行为|编辑器行为|
|-|-|-|
|Error|冲突显示为*错误*中**错误列表**和在命令行生成输出，并且会导致生成失败。|有问题代码带有红色波浪，且滚动条中的小红色框标记为带有下划线。|
|警告|冲突显示为*警告*中**错误列表**和在命令行生成输出，但不是会导致生成失败。|有问题代码使用绿色波浪，且滚动条中的小绿色框标记为带有下划线。|
|T:System.Diagnostics.Switch|冲突显示为*消息*中**错误列表**，根本不在命令行生成输出。|有问题代码是用灰色波浪，且标记为滚动条中的小灰色框带下划线。|
|Hidden|非-对用户可见。|非-对用户可见。 诊断报告给 IDE 诊断引擎，但是。|
|无|完全禁止。|完全禁止。|

此外，你可以"重置"规则的严重性通过将它设置为**默认**。 每个诊断具有可在中查看的默认严重性**属性**窗口。

下面的屏幕截图显示在代码编辑器中，三个不同的严重级别的三个不同的诊断冲突。 请注意波浪，以及在右侧的滚动条中的小框的颜色。

![在代码编辑器中的错误、 警告和信息冲突](media/diagnostics-severity-colors.png)

下面的屏幕截图显示相同的三个冲突，按它们出现在**错误列表**:

![错误列表中的错误、 警告和信息冲突](media/diagnostics-severities-in-error-list.png)

你可以更改规则的严重性**解决方案资源管理器**，或者放在 *\<projectname >.ruleset*后更改的重要程度中的规则添加到解决方案的文件**解决方案资源管理器**。

![在解决方案资源管理器中的规则集文件](media/ruleset-in-solution-explorer.png)

### <a name="to-set-rule-severity-from-solution-explorer"></a>若要从解决方案资源管理器中设置规则严重性

1. 在**解决方案资源管理器**，展开**引用** > **分析器**(**依赖关系** >  **分析器**有关.NET Core 项目)。

1. 展开包含你想要设置的严重性的规则的程序集。

1. 右键单击规则并选择**设置规则设置严重性**。 在弹出菜单中，选择严重性选项之一。

   规则的严重性将保存在活动规则集文件。

### <a name="to-set-rule-severity-in-the-rule-set-file"></a>若要设置规则规则中的严重性设置文件

1. 打开规则集文件通过双击它在**解决方案资源管理器**，选择**打开活动规则集**的右键单击菜单上**分析器**节点，或通过选择**打开**上**代码分析**项目的属性页。

1. 通过展开其包含的程序集，浏览到该规则。

1. 在**操作**列中，选择要打开下拉列表中的值，并从列表中选择所需的严重性。

   ![在编辑器中打开的规则集文件](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>禁止显示冲突

有多种方法来禁止显示规则冲突：

- 若要禁止显示所有当前的冲突，请选择**分析** > **运行代码分析和禁止显示活动问题**菜单栏上。 这有时称为"基线"。

- 若要禁止显示从诊断**解决方案资源管理器**，设置其严重性为**无**。

- 若要禁止显示从规则集编辑器诊断，请取消选中其名称旁边的框，或设置**操作**到**无**。

- 若要禁止显示代码编辑器中的诊断，请将光标放在代码行中使用冲突和按**Ctrl**+**。** 若要打开**快速操作**菜单。 选择**禁止显示 CAxxxx** > **源中**或**禁止显示 CAxxxx** > **在禁止显示文件**。

   ![禁止显示诊断从快速操作菜单](media/suppress-diagnostic-from-editor.png)

- 若要禁止显示从诊断**错误列表**、 错误、 警告或消息中，右键单击并选择**禁止** > **在源**或**禁止显示** > **在禁止显示文件**。

   - 如果你选择**在源**、**预览更改**对话框将打开，其中显示的 C# 预览[#pragma 警告](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning)或 Visual Basic [#Disable 警告](/dotnet/visual-basic/language-reference/directives/directives)指令添加到源代码。

      ![在代码文件中添加 #pragma 警告的预览](media/pragma-warning-preview.png)

   - 如果你选择**在禁止显示文件**、**预览更改**对话框将打开，其中显示的预览<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>添加到全局禁止显示文件的属性。

      ![将 SuppressMessage 特性添加到禁止显示文件的预览](media/preview-changes-in-suppression-file.png)

   在**预览更改**对话框中，选择**应用**。

> [!NOTE]
> 在.NET Core 项目中，如果添加对具有 NuGet 分析器的项目的引用这些分析器将自动添加到依赖项目太。 若要禁用此行为，例如如果依赖项目为单元测试项目中，将标记为私有中的 NuGet 包 *.csproj*或 *.vbproj*引用项目文件：
>
> ```xml
> <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.6.0" PrivateAssets="all" />
> ```

## <a name="see-also"></a>请参阅

- [Roslyn 分析器在 Visual Studio 中的概述](../code-quality/roslyn-analyzers-overview.md)
- [提交 Roslyn 分析器 bug](https://github.com/dotnet/roslyn-analyzers/issues)
- [使用规则集](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [禁止显示代码分析警告](../code-quality/in-source-suppression-overview.md)