---
title: "面向 .NET 开发者的 Visual Studio 2017 | Microsoft Docs"
description: "概述 Visual Studio 2017 功能如何帮助用户更快编写更好的 .NET 代码。"
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.technology: vs-ide-general
ms.date: 01/16/2018
ms.topic: article
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: be14af66f5aa5389e9e701eb79dc68ee733c6068
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="visual-studio-2017-for-net-developers"></a>面向 .NET 开发者的 Visual Studio 2017

## <a name="smart-code-editor"></a>智能代码编辑器

- [文档：使用 IntelliSense](using-intellisense.md)
- [文档：智能编辑器功能](writing-code-in-the-code-and-text-editor.md)

Visual Studio 通过 .NET（“Roslyn”）编译器深入理解代码，为用户提供众多智能编辑功能，比如语法着色、代码完成、拼写检查错误输入的变量、未导入的类型解析、大纲显示、结构可视化工具、[CodeLens](find-code-changes-and-other-history-with-codelens.md)、调用层次结构、可悬停的快速信息、参数帮助，以及用于重构、应用快速操作和生成代码的各种工具。

![Visual Studio 智能代码编辑器](../ide/media/VSIDE_Productivity_SmartCodeEditor.png "VSIDE_Productivity_SmartCodeEditor")

## <a name="navigate-and-search-your-codebase"></a>导航并搜索基本代码

[文档：导航代码](navigating-code.md)

使用“转到全部”快捷方式 (**Ctrl+T**) 跳转到任意文件、类型、成员或符号声明，从而快速导航 .NET 代码。 在代码中查找符号或文本的所有引用，其中包括跨 .NET 语言的引用 (**Shift+F12**)。 使用目标导航命令可直接跳转到符号定义 (**F12**) 或实现 (**Ctrl+F12**)。

![转到全部和查找所有引用](../ide/media/VSIDE_Productivity_Navigation.png "VSIDE_Productivity_Navigation")

## <a name="live-code-analysis-for-code-quality"></a>代码质量的实时代码分析

[文档：重构和快速操作](refactoring-code-generation-quick-actions.md)

Visual Studio 提供实时代码诊断，通过检测错误和可能有问题的代码，帮助提高代码质量。 我们提供快速操作 (Ctrl+.)，可解决跨文档、项目或解决方案检测到的问题。 启用*完整解决方案分析*可在整个解决方案中查找问题，即使未在编辑器中打开这些文件也是如此。

此外，使用 Ctrl+. 快捷方式，还可从代码建议中了解最佳做法、存根或生成代码、重构代码 以更正样式问题。

![使用灯泡菜单应用快速修复和重构](../ide/media/VSIDE_Productivity_CodeAnalysis.png "VSIDE_Productivity_CodeAnalysis")

## <a name="unit-testing"></a>单元测试

[文档：Visual Studio 中的单元测试](../test/improve-code-quality.md)

基于 MSTest、NUnit 或 XUnit 测试框架，为面向 .NET Framework、.NET Standard 或 .NET Core 的任何应用程序运行和调试单元测试。 在*测试资源管理器*中浏览并查看测试，或使用 *Live Unit Testing*（仅适用于企业版 SKU）在编辑器内实时查看代码更改对单元测试的影响。

![Visual Studio 中的 Live Unit Testing](../ide/media/VSIDE_Productivity_LiveUnitTesting.png "VSIDE_Productivity_LiveUnitTesting")

## <a name="code-consistency-and-style"></a>代码一致性和样式

- [文档：可移植的自定义编辑器选项](create-portable-custom-editor-options.md)
- [文档：用于 .NET 的 EditorConfig 代码样式设置](editorconfig-code-style-settings-reference.md)

Visual Studio 支持编码约定配置，检测编码样式冲突，并使用 Ctrl+. 快捷方式提供快速修复 以更正样式问题。 使用 *EditorConfig* 可在存储库中配置并强制实施团队的格式设置、命名和代码样式约定，允许覆盖项目和文件级别的值。

![使用 EditorConfig 配置并强制实施编码约定](../ide/media/VSIDE_Productivity_CodeStyle.png "VSIDE_Productivity_CodeStyle")

## <a name="debugging"></a>调试

[文档：Visual Studio 中的调试](../debugger/index.md)

Visual Studio 提供一流的调试器，可调试面向 .NET Framework、.NET Standard 和 .NET Core 的 .NET 应用程序。 可切换和设置条件断点 (**F9**)，单步执行（进入过程）方法调用，计算 LINQ 和 lambda 表达式，设置变量监视，重新附加到进程，检查调用堆栈，甚至使用“编辑并继续”在调试时实时编辑代码。

如果服务在 Azure 中运行，使用 Visual Studio 2017 Enterprise 中的*快照调试*可诊断已部署的实时云应用程序上的问题。

![Visual Studio 中的调试](../ide/media/VSIDE_Productivity_Debugging.png "VSIDE_Productivity_Debugging")

## <a name="version-control"></a>版本控制

[文档：Visual Studio 中的版本控制](/vsts/index)

可使用 git 或 TFVC 在 Visual Studio 中存储和更新代码。 在编辑器中，可利用团队资源管理器整理本地更改，并使用状态栏跟踪挂起的提交和更改。 可在 Visual Studio 中通过[用于 Visual Studio 的持续交付工具](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio)扩展设置持续集成和交付，以采用敏捷开发者工作流。

![Visual Studio 中的源代码管理] (../ide/media/VSIDE_Productivity_SourceControl.png "VSIDE_Productivity_SourceControl")

## <a name="extensibility"></a>扩展性

[文档：扩展 Visual Studio](../extensibility/index.md)

Visual Studio 具有一个丰富的扩展生态系统，可在需要时安装或创建扩展。 从*扩展库*或 *Visual Studio Marketplace* 安装扩展，使用 *VS SDK* 生成自己的编辑器插件，或使用 *.NET 编译器平台 SDK* 创建自己的实时代码分析器或重构。 可通过下载 [Microsoft 代码分析](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017)扩展，查找附加代码修复和建议。

![Visual Studio 扩展库](../ide/media/VSIDE_Productivity_Extensibility.png "VSIDE_Productivity_Extensibility")

## <a name="popular-extensions--shortcuts"></a>热门扩展和快捷方式

如果用户来自另一个 IDE 或编码环境，可能会发现安装以下某个扩展很有用：

- [Emacs 模拟](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation )
- [适用于 Visual Studio 的 HotKeys (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

以下是常用的 Visual Studio 快捷方式。 请注意，某些扩展会取消绑定默认 Visual Studio 键绑定，必须还原键绑定以使用以下命令。 若要将键绑定还原为 Visual Studio 的默认值，请转到“工具”>“导入和导出设置…”>“重置所有设置”。

| 快捷方式（所有配置文件） | 命令 | 描述 |
|-|-|-|
| **Ctrl+T** | 转到全部 | 导航到任何文件/类型/成员/符号声明 |
| **F12**（也可使用 **Ctrl+单击**） | 转到定义 | 导航到定义符号的位置 |
| **Ctrl+F12** | 转到实现 | 从基类型或基成员导航到各种实现 |
| **Shift+F12** | 查找所有引用 | 查看所有符号或文本引用 |
| Ctrl+. （也可使用 C# 配置文件中的 **Alt+Enter**） | 快速操作和重构 | 查看光标位置或代码选定内容处可用的代码修复、代码生成操作、重构或其他快速操作 |
| **Ctrl**+**E**、**V** | 复制行 | 复制光标所在的代码行（适用于 Visual Studio 2017 版本 15.6  及更高版本） |
| **Ctrl+Q** | 快速启动 | 搜索所有 Visual Studio 设置 |
| **F5** | 开始调试 | 开始调试应用程序 |
| **Ctrl+F5** | 不进行调试直接运行 | 不进行调试，直接在本地运行应用程序 |
| **Ctrl+K,D**（默认配置文件）或 **Ctrl+E,D**（C# 配置文件） | 设置文档的格式 | 基于换行、间距和缩进设置，清理文件中的格式设置冲突 |
| Ctrl+,E（默认配置文件）或 Ctrl+W,E（C# 配置文件）**\\** | 查看错误列表 | 查看文档、项目或解决方案中的所有错误 |