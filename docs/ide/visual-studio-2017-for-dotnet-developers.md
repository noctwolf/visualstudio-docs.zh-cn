---
title: 提高 .NET 开发工作效率
description: 概述导航、代码分析、单元测试和其他功能，帮助提升编写 .NET 代码的速度和质量。
author: kuhlenh
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.date: 06/14/2018
ms.topic: conceptual
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: 5a2158663defe02dc51e91e888d47f325db7226a
ms.sourcegitcommit: 20d1b9a5bf041bb28453501eb63bc0537a8e4f54
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2018
ms.locfileid: "51645141"
---
# <a name="visual-studio-2017-c-productivity-guide"></a>Visual Studio 2017 C# 工作效率指南

了解 [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 如何提高开发人员的工作效率。 充分利用性能和生产效率改进，如：导航到反编译程序集、键入时的变量名称建议、“测试资源管理器”中的层次结构视图、“转到全部”(Ctrl+T) 导航到文件/类型/成员/符号声明、智能“异常帮助程序”、代码样式配置和执行、以及众多重构和代码修补程序。

## <a name="im-used-to-my-keyboard-shortcuts-from-a-different-extensioneditoride"></a>我已经习惯了不同扩展/编辑器/IDE 的键盘快捷方式

**Visual Studio 2017 版本 15.8 中的新增内容** 如果来自其他 IDE 或编码环境，可将键盘方案更改为 Visual Studio Code 或 ReSharper (Visual Studio)：

![Visual Studio 中的键盘方案](../ide/media/VS2017Guide-Keyboard.png)

某些扩展也提供键盘方案：

- [适用于 Visual Studio 的 HotKeys (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [Emacs 模拟](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

Visual Studio 常用快捷方式如下：

| 快捷方式（所有配置文件） | 命令 | 描述 |
|-|-|-|
| Ctrl + T | 转到全部 | 导航到任何文件/类型/成员/符号声明 |
| F12（也可使用 Ctrl+单击） | 转到定义 | 导航到定义符号的位置 |
| Ctrl+F12 | 转到实现 | 从基类型或基成员导航到各种实现 |
| Shift+F12 | 查找所有引用 | 查看所有符号或文本引用 |
| Ctrl+. （也可使用 C# 配置文件中的 Alt+Enter） | 快速操作和重构 | 查看光标位置或代码选定内容处可用的代码修复、代码生成操作、重构或其他快速操作 |
| **Ctrl**+**D** | 复制行 | 复制光标所在的代码行（适用于 Visual Studio 2017 版本 15.6  及更高版本） |
| **Shift**+**Alt**+**+**/**-** | 扩大/收缩选定内容 | 在编辑器中扩大或收缩当前选定内容（适用于 Visual Studio 2017 版本 15.5 及更高版本） |
| **Shift** + **Alt** + **.** | 插入下一个匹配的脱字号 | 在与当前选择匹配的下一个位置添加选择和脱字号（适用于 Visual Studio 2017 版本 15.8 及更高版本） |
| Ctrl+Q | 快速启动 | 搜索所有 Visual Studio 设置 |
| **F5** | 开始调试 | 开始调试应用程序 |
| Ctrl+F5 | 不进行调试直接运行 | 不进行调试，直接在本地运行应用程序 |
| Ctrl+K,D（默认配置文件）或 Ctrl+E,D（C# 配置文件） | [设置文档格式](code-styles-and-quick-actions.md#format-document-command) | 基于换行、间距和缩进设置，清理文件中的格式设置冲突 |
| Ctrl+\\、Ctrl+E（默认配置文件）或 Ctrl+W,E（C# 配置文件） | 查看错误列表 | 查看文档、项目或解决方案中的所有错误 |
| **Alt** + **PgUp/PgDn** | 转到下一个/上一个问题 | 跳转到文档中的上一个/下一个错误、警告和建议（适用于 Visual Studio 2017 版本 15.8 及更高版本） |

> [!NOTE]
> 一些扩展取消绑定默认的 Visual Studio 键绑定。 若要使用以上命令，请按以下方式将键绑定还原为 Visual Studio 默认设置：转到“工具” > “导入和导出设置” > “重置所有设置”，或转到“工具” > “选项” > “键盘” > “重置”。

参阅[我们的文档](../ide/tips-and-tricks-for-visual-studio.md)了解 Visual Studio 中的更多键盘快捷键和命令。

## <a name="i-need-a-way-to-quickly-navigate-to-files-or-types"></a>我需要一种快速导航到文件或类型的方法

Visual Studio 2017 有一种名为“转到全部”(Ctrl+T) 的功能。 通过“转到全部”可快速跳转到任何文件、类型、成员或符号声明。

- 更改此搜索栏的位置或使用“齿轮”图标关闭“实时导航预览”。
- 使用查询语法（例如“t mytype”）筛选结果。 还可以将搜索范围限定在当前文档。
- 支持 camelCase 匹配！

![Visual Studio 中的转到全部](../ide/media/VS2017Guide-go-to-all.png)

## <a name="my-team-enforces-code-style-rules-on-our-codebase"></a>我的团队对基本代码强制实施代码样式规则

可以使用 .editorconfig 文件编写编码约定，并使其跟随源。

- 可以安装 [EditorConfig 语言服务扩展](https://aka.ms/editorconfig)，以轻松地在 Visual Studio 中添加和编辑 .editorconfig 文件。
- 试用 [Visual Studio 的 IntelliCode 扩展](/visualstudio/intellicode/intellicode-visual-studio)。 此试验性扩展从现有代码中推断出你的代码样式，然后创建一个非空的 .editorconfig 文件，并且已定义代码样式首选项。
- 签出所有 [.NET 编码约定选项](https://aka.ms/editorconfigDocs)文档。
- 查看[此要点](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8)获取示例 .editorconfig 文件。

![Visual Studio 中的代码样式实施](../ide/media/VSGuide_CodeStyle.png)

## <a name="i-need-more-refactorings-and-code-fixes"></a>我需要更多重构和代码修补程序

Visual Studio 2017 包含大量重构、代码生成操作和代码修补程序。 红色波浪线表示错误，绿色波浪线表示警告，三个灰色点表示代码建议。 若要访问代码修补程序，可以单击灯泡/螺丝刀图标或按 Ctrl+.  或 Alt+Enter。 每个修补程序都附带一个显示修补工作方式实时代码差异的预览窗口。

- 常用的快速修复和重构包括：
  - *重命名*
  - *提取方法*
  - *更改方法签名*
  - *生成构造函数*
  - *生成方法*
  - 将类型移动到文件
  - 添加 NULL 检查
  - 添加参数
  - 删除不必要的 Using
  - 请阅读[文档](https://aka.ms/refactorings)，查看详细信息
- 使用 [Roslyn 分析器](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix)编写自己的重构或代码修补程序。
- 有几个社区成员写了一些免费扩展，这些扩展添加了其他的代码检查：
  - [FXCop 分析器](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/)
  - [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017)
  - [SonarLint for Visual Studio](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017)
  - [StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/)

![在 Visual Studio 中重构](../ide/media/VSGuide_CodeAnalysis.png)

## <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>我需要“查找使用情况”、“转到实现”、“导航到反编译程序集”

Visual Studio 2017 具有许多功能可帮助你搜索和导航基本代码。 详细了解[代码导航功能](../ide/navigating-code.md)

| 功能 | 快捷键 | 详细信息/改进 |
|- | - | -|
| 查找所有引用 | Shift+F12| 结果已着色，可按项目、定义等分组。还可“锁定”结果。 |
| 转到实现 | Ctrl+F12 | 可以对 `override` 关键字使用转到定义来导航到重写成员 |
| 转到定义 | F12 或 Ctrl+单击| 按住 Ctrl，同时单击以导航到定义 |
| 查看定义 | Alt+F12 | 定义的内联视图 |
| 结构可视化工具 | 括号中的灰色虚线 | 悬停鼠标查看代码结构 |
| 导航到反编译的程序集 | F12 或 Ctrl+单击 | 通过启用以下功能导航到外部源（使用 ILSpy 反编译）：“工具” > “选项” > “文本编辑器” > “C#” > “高级” > “启用导航到反编译源”。 |

![转到全部和查找所有引用](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="i-want-to-run-and-see-my-unit-tests"></a>我想要运行并查看我的单元测试

我们在 Visual Studio 2017 中对测试体验进行了大量改进。 在 MSTest v1、MSTest v2、NUnit 或 XUnit 测试框架中使用任一单元测试体验。

- 15.6 版中的 **Test Explorer** 测试发现非常快速（为获得最佳结果，请升级到最新版本的测试适配器）。
- 在 15.6 版中使用新的分层排序组织 Test Explorer 中的测试。
- [Live Unit Testing](../test/live-unit-testing.md) 持续运行受代码更改影响的测试并更新内联编辑器图标以显示测试的状态。 包含或排除实时测试集中的特定测试或测试项目。

![Visual Studio 中的文本资源管理器的层次结构视图](../ide/media/VSGuide_Testing.png)

## <a name="i-want-to-debug-my-code"></a>我想要调试代码

我们已在 Visual Studio 2017 中添加了大量新的调试功能：

- “运行到点击位置”功能具有以下作用：你将鼠标悬停在一行代码旁，点击出现的绿色“运行”图标，则程序会运行到该行停止。
- 新的异常帮助程序将最重要的信息（如哪些变量在 NullReferenceException 中是“NULL”）置于对话框顶层。
- [后退](../debugger/how-to-use-intellitrace-step-back.md)让你可以返回到上一个断点或步骤，并查看当时应用程序的状态。
- [快照调试](/azure/application-insights/app-insights-snapshot-debugger)让你可以在引发异常时调查实时 Web 应用的状态（必须是在 Azure 上）。

![Visual Studio 2017 中的新异常帮助程序](../ide/media/VSGuide_Debugging.png)

## <a name="i-want-to-use-version-control-with-my-projects"></a>我想要在项目中使用版本控制

可以使用 git 或 TFVC 在 Visual Studio 中存储和更新代码。

- 利用团队资源管理器整理本地更改，并使用状态栏跟踪挂起的提交和更改。
- 在 Visual Studio 中通过 [Visual Studio 持续交付工具](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio)扩展设置项目的持续集成和交付，以采用敏捷开发者工作流。

![Visual Studio 中的源控件](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-do-i-need-to-know-about"></a>我还需要知道其他哪些功能？

下面是提升写代码效率的编辑器和工作效率功能列表。 可能需要启用某些功能，因为它们默认是关闭的（它们可能在计算机上检索内容、具有争议性或者当前处在试验阶段）。

| 功能 | 详细信息 | 如何启用 |
|-|-|-|
| 在解决方案资源管理器中查找文件 | 突出显示了解决方案资源管理器中活动的文件 | “工具” > “选项” > “项目和解决方案” > “跟踪解决方案资源管理器中的活动项” |
| 为引用程序集和 NuGet 包中的类型添加 using | 显示灯泡和代码修补程序，对未引用的类型安装 NuGet 包 | “工具” > “选项” > “文本编辑器” > “C#” > “高级” > “建议对引用程序集中的类型使用 using”和“建议对 NuGet 包中的类型使用 using” |
| 启用完整解决方案分析 | 请在错误列表中查看解决方案中的所有错误 | “工具” > “选项” > “文本编辑器” > “C#” > “高级” > “启用完整解决方案分析” |
| 启用导航到反编译源 | 对外部源的类型/成员启用“转到定义”并使用 ILSpy 反编译程序显示方法体 | “工具” > “选项” > “文本编辑器” > “C#” > “高级” > “启用导航到反编译源” |
| 完成/建议模式 | 更改 IntelliSense 中的完成行为 - 有 IntelliJ 背景的开发人员往往会更改此处的默认设置 | “菜单” > “编辑” > “IntelliSense” > “切换完成模式” |
| [CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md) | 显示编辑器中的代码引用信息和更改历史记录 | “工具” > “选项” > “文本编辑器” > “所有语言” > “CodeLens” |
| [代码片段](../ide/visual-csharp-code-snippets.md) | 帮助去掉常见样本 | 键入代码片段名称，然后按两次 Tab。 |

## <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>缺少提供工作效率的功能或性能体验较差？

可通过以下几种方式提供反馈：

- 前往 [GitHub 存储库](https://github.com/dotnet/roslyn/issues)提交 .NET 功能请求。
- 使用 Visual Studio 窗口右上方的“发送反馈”图标提交 Visual Studio 功能请求、bug 和性能问题。
