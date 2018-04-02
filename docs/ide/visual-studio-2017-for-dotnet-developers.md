---
title: 面向 .NET 开发者的 Visual Studio 2017 | Microsoft Docs
description: 概述 Visual Studio 2017 功能如何帮助用户更快编写更好的 .NET 代码。
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
ms.openlocfilehash: 7e910c50682d45d209d993cb883ca01d1ea436f2
ms.sourcegitcommit: 236c250bb97abdab99d00c6525d106fc0035d7d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2018
---
# <a name="visual-studio-2017-productivity-guide-for-net-developers"></a>适用于 .NET 开发人员的 Visual Studio 2017 工作效率指南

- [工作效率指南](#guide)
- [Visual Studio 2017 概述](#overview)

## <a name="a-idguide-productivity-guide"></a><a id="guide"/> 工作效率指南
[Visual Studio 2017](https://www.visualstudio.com/downloads/) 使开发人员工作更为高效！ 改进了解决方案启动和加载、测试发现以及键入时延迟问题的性能和可靠性。 此外，还添加并增强了有助于更快更好地写入代码的功能。 这些功能包括：导航到反编译程序集、键入的变量名称建议、测试资源管理器中的层次结构视图、“转到全部”(Ctrl+T) 导航到文件/类型/成员/符号声明、智能异常帮助程序、代码类型配置和执行、以及众多重构和代码修补程序。 

按照本指南优化工作效率。

###  <a name="im-used-to-my-keyboard-shortcuts-from-a-different-extensioneditoride"></a>我已经习惯了不同扩展/编辑器/IDE 的键盘快捷方式。

如果用户来自另一个 IDE 或编码环境，可能会发现安装以下某个扩展很有用：

- [Emacs 模拟](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [适用于 Visual Studio 的 HotKeys (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

以下是常用的 Visual Studio 快捷方式。 

> [!NOTE]
> 某些扩展取消绑定默认的 Visual Studio 键绑定，因此必须使用以下命令还原它们。 通过以下方式将键绑定还原到 Visual Studio 默认值：“工具”>“导入和导出设置...”>“重置所有设置”，或“工具”>“选项”>“键盘”>“重置”。

| 快捷方式（所有配置文件） | 命令 | 描述 |
|-|-|-|
| **Ctrl+T** | 转到全部 | 导航到任何文件/类型/成员/符号声明 |
| **F12**（也可使用 **Ctrl+单击**） | 转到定义 | 导航到定义符号的位置 |
| **Ctrl+F12** | 转到实现 | 从基类型或基成员导航到各种实现 |
| **Shift+F12** | 查找所有引用 | 查看所有符号或文本引用 |
| Ctrl+. （也可使用 C# 配置文件中的 **Alt+Enter**） | 快速操作和重构 | 查看光标位置或代码选定内容处可用的代码修复、代码生成操作、重构或其他快速操作 |
| **Ctrl**+**D** | 复制行 | 复制光标所在的代码行（适用于 Visual Studio 2017 版本 15.6  及更高版本） |
| **Shift**+**Alt**+**+**/**-** | 扩大/收缩选定内容 | 在编辑器中扩大或收缩当前选定内容（适用于 Visual Studio 2017 版本 15.5 及更高版本） |
| **Ctrl+Q** | 快速启动 | 搜索所有 Visual Studio 设置 |
| **F5** | 开始调试 | 开始调试应用程序 |
| **Ctrl+F5** | 不进行调试直接运行 | 不进行调试，直接在本地运行应用程序 |
| **Ctrl+K,D**（默认配置文件）或 **Ctrl+E,D**（C# 配置文件） | 设置文档的格式 | 基于换行、间距和缩进设置，清理文件中的格式设置冲突 |
| Ctrl+,E（默认配置文件）或 Ctrl+W,E（C# 配置文件）**\\** | 查看错误列表 | 查看文档、项目或解决方案中的所有错误 |

### <a name="i-need-a-way-to-quickly-navigate-to-files-or-types"></a>我需要一种快速导航到文件或类型的方法。
Visual Studio 2017 有一种名为“转到全部”(Ctrl+T) 的功能。 通过“转到全部”可快速跳转到任何文件、类型、成员或符号声明。
- 更改此搜索栏的位置或使用“齿轮”图标关闭“实时导航预览”
- 使用查询语法（例如“t mytype”）筛选结果。 还可以将搜索范围限定在当前文档。
- 支持 camelCase 匹配！

![Visual Studio 中的“转到全部”](../ide/media/VS2017Guide-go-to-all.png "VS2017Guide-go-to-all")

### <a name="my-team-enforces-code-style-rules-on-our-codebase"></a>我的团队对基本代码强制实施代码样式规则。
可以使用 .editorconfig 文件编写编码约定。 建议安装 [EditorConfig 语言服务扩展](https://aka.ms/editorconfig)，以用于添加和编辑 .editorconfig 文件。 建议签出所有 .NET 编码约定选项的[文档](https://aka.ms/editorconfigDocs)。

签出[此要点](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8)获取示例 .editorconfig。

![Visual Studio 中的代码样式实施](../ide/media/VS2017Guide-code-style.png "VS2017Guide-code-style")

### <a name="i-need-more-refactorings-and-code-fixes"></a>我需要更多重构和代码修补程序。
Visual Studio 2017 包含大量重构、代码生成操作和代码修补程序，可在此[文档](https://aka.ms/refactorings)中查看。 红色波浪线表示错误，绿色波浪线表示警告，三个灰色点表示代码建议。

若要访问代码修补程序，可以单击灯泡/螺丝刀图标或按 Ctrl+.  或 Alt+Enter。 每个修补程序都附带一个显示修补工作方式实时代码差异的预览窗口。

下面是一些常用的快速修补程序和重构：重命名、提取方法、更改方法签名、生成构造函数、生成方法、将类型移动到文件、添加 Null 检查、添加参数、删除不必要的 Using。

可以使用 [Roslyn 分析器](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix)轻松写出重构和代码修补程序。 有几个社区成员写了一些免费扩展，这些扩展添加了其他的代码检查：用于 Visual Studio 的 Roslynator 和 SonarLint。 

![Visual Studio 中的重构](../ide/media/VS2017Guide-refactoring.png "VS2017Guide-refactoring")

### <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>我需要“查找使用情况”、“转到实现”、“导航到反编译程序集”
Visual Studio 2017 中包含许多有助于搜索和导航基本代码的功能，包括“查找所有引用”(Shift+F12)、“转到实现”(Ctrl+F12)、“转到定义”（F12 或按住 Ctrl 单击）。 版本 15.6 中已添加“导航到反编译程序集”。 要打开此功能，请转到“工具”>“选项”>“文本编辑器”>“C#”>“高级”>“启用导航到反编译源”。

![Visual Studio 中的“导航到反编译源”](../ide/media/VS2017Guide-navigate-to-source.png "VS2017Guide-navigate-to-source")

### <a name="i-want-to-run-and-see-my-unit-tests"></a>我想要运行并查看我的单元测试。
Visual Studio 2017 针对单元测试提供了两种功能：测试资源管理器和 Live Unit Testing。 在测试资源管理器 15.6 版本中，我们极大地提升了测试发现速度。 我们还重新设计了用于分层排序的 UI。

Visual Studio 还有一个名为 [Live Unit Testing](/test/live-unit-testing) 的单元测试功能。 Live Unit Testing 在后台持续运行、运行代码更改影响的测试并更新内联编辑器图标以显示测试的状态。

![Visual Studio 中文本资源管理器的层次结构视图](../ide/media/VS2017Guide-hiearchy-test-explorer.png "VS2017Guide-hiearchy-test-explorer")

### <a name="what-other-features-do-i-need-to-know-about"></a>我还需要知道其他哪些功能？
下面是提升写代码效率的编辑器和工作效率功能列表。 可能需要启用某些功能，因为它们默认是关闭的（它们可能在计算机上检索内容、具有争议性或者当前处在试验阶段）。
- “在解决方案资源管理器中查找文件”突出显示了解决方案资源管理器中活动的文件。
  - “工具”>“选项”>“项目和解决方案”>“跟踪解决方案资源管理器中的活动项”
- “为引用程序集和 NuGet 包中的类型添加 using”显示附带代码修补程序的灯泡，用于为未引用的类型安装 NuGet 包。
  - “工具”>“选项”>“文本编辑器”>“C#”>“高级”>“建议对引用程序集中的类型使用 using”和“建议对 NuGet 包中的类型使用 using”
- “启用完整解决方案分析”，用于查看错误列表中解决方案的所有错误。
  - “工具”>“选项”>“文本编辑器”>“C#”>“高级”>“启用完整解决方案分析”
- “启用导航到反编译源”，用于启用外部源类型/成员上的“转到定义”并使用 ILSpy 反编译程序显示方法体。
  - “工具”>“选项”>“文本编辑器”>“C#”>“高级”>“启用导航到反编译源”
- IntelliSense 中的“编译/建议模式”，用于更改完成行为。 有 IntelliJ 背景的开发人员往往会更改此处的默认设置。
  - “菜单”>“编辑”>“IntelliSense”->“切换完成模式”
- 我们提供有“代码片段”，用于去掉常见样本（按两次 Tab）。 请参阅[完整列表](/ide/visual-csharp-code-snippets)。

![Visual Studio 中的代码片段](../ide/media/VS2017Guide-code-snippet.png "VS2017Guide-code-snippet")

### <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>缺少提供工作效率的功能或性能体验较差？
可通过以下几种方式提供反馈：
- 前往 [GitHub 存储库](https://github.com/dotnet/roslyn/issues)提交 .NET 功能请求。
- 使用 Visual Studio 窗口顶部的“发送反馈”图标提交 Visual Studio 功能请求、bug 和性能问题。


## <a name="a-idoverview-overview-of-visual-studio-2017-for-net-developers"></a><a id="overview"/> 面向 .NET 开发者的 Visual Studio 2017 概述

### <a name="smart-code-editor"></a>智能代码编辑器

- [文档：使用 IntelliSense](using-intellisense.md)
- [文档：智能编辑器功能](writing-code-in-the-code-and-text-editor.md)

Visual Studio 通过 .NET（“Roslyn”）编译器深入理解代码，为用户提供众多智能编辑功能，比如语法着色、代码完成、拼写检查错误输入的变量、未导入的类型解析、大纲显示、结构可视化工具、[CodeLens](find-code-changes-and-other-history-with-codelens.md)、调用层次结构、可悬停的快速信息、参数帮助，以及用于重构、应用快速操作和生成代码的各种工具。

![Visual Studio 智能代码编辑器](../ide/media/VSIDE_Productivity_SmartCodeEditor.png "VSIDE_Productivity_SmartCodeEditor")

### <a name="navigate-and-search-your-codebase"></a>导航并搜索基本代码

[文档：导航代码](navigating-code.md)

使用“转到全部”快捷方式 (**Ctrl+T**) 跳转到任意文件、类型、成员或符号声明，从而快速导航 .NET 代码。 在代码中查找符号或文本的所有引用，其中包括跨 .NET 语言的引用 (**Shift+F12**)。 使用目标导航命令可直接跳转到符号定义 (**F12**) 或实现 (**Ctrl+F12**)。

![转到全部和查找所有引用](../ide/media/VSIDE_Productivity_Navigation.png "VSIDE_Productivity_Navigation")

### <a name="live-code-analysis-for-code-quality"></a>代码质量的实时代码分析

[文档：重构和快速操作](refactoring-code-generation-quick-actions.md)

Visual Studio 提供实时代码诊断，通过检测错误和可能有问题的代码，帮助提高代码质量。 我们提供快速操作 (Ctrl+.)，可解决跨文档、项目或解决方案检测到的问题。 启用*完整解决方案分析*可在整个解决方案中查找问题，即使未在编辑器中打开这些文件也是如此。

此外，使用 Ctrl+. 快捷方式，还可从代码建议中了解最佳做法、存根或生成代码、重构代码 以更正样式问题。

![使用灯泡菜单应用快速修复和重构](../ide/media/VSIDE_Productivity_CodeAnalysis.png "VSIDE_Productivity_CodeAnalysis")

### <a name="unit-testing"></a>单元测试

[文档：Visual Studio 中的单元测试](../test/improve-code-quality.md)

基于 MSTest、NUnit 或 XUnit 测试框架，为面向 .NET Framework、.NET Standard 或 .NET Core 的任何应用程序运行和调试单元测试。 在*测试资源管理器*中浏览并查看测试，或使用 *Live Unit Testing*（仅适用于企业版 SKU）在编辑器内实时查看代码更改对单元测试的影响。

![Visual Studio 中的 Live Unit Testing](../ide/media/VSIDE_Productivity_LiveUnitTesting.png "VSIDE_Productivity_LiveUnitTesting")

### <a name="code-consistency-and-style"></a>代码一致性和样式

- [文档：可移植的自定义编辑器选项](create-portable-custom-editor-options.md)
- [文档：用于 .NET 的 EditorConfig 代码样式设置](editorconfig-code-style-settings-reference.md)

Visual Studio 支持编码约定配置，检测编码样式冲突，并使用 Ctrl+. 快捷方式提供快速修复 以更正样式问题。 使用 *EditorConfig* 可在存储库中配置并强制实施团队的格式设置、命名和代码样式约定，允许覆盖项目和文件级别的值。

![使用 EditorConfig 配置并强制实施编码约定](../ide/media/VSIDE_Productivity_CodeStyle.png "VSIDE_Productivity_CodeStyle")

### <a name="debugging"></a>调试

[文档：Visual Studio 中的调试](../debugger/index.md)

Visual Studio 提供一流的调试器，可调试面向 .NET Framework、.NET Standard 和 .NET Core 的 .NET 应用程序。 可切换和设置条件断点 (**F9**)，单步执行（进入过程）方法调用，计算 LINQ 和 lambda 表达式，设置变量监视，重新附加到进程，检查调用堆栈，甚至使用“编辑并继续”在调试时实时编辑代码。

如果服务在 Azure 中运行，使用 Visual Studio 2017 Enterprise 中的*快照调试*可诊断已部署的实时云应用程序上的问题。

![Visual Studio 中的调试](../ide/media/VSIDE_Productivity_Debugging.png "VSIDE_Productivity_Debugging")

### <a name="version-control"></a>版本控制

[文档：Visual Studio 中的版本控制](/vsts/index)

可使用 git 或 TFVC 在 Visual Studio 中存储和更新代码。 在编辑器中，可利用团队资源管理器整理本地更改，并使用状态栏跟踪挂起的提交和更改。 可在 Visual Studio 中通过[用于 Visual Studio 的持续交付工具](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio)扩展设置持续集成和交付，以采用敏捷开发者工作流。

![Visual Studio 中的源代码管理] (../ide/media/VSIDE_Productivity_SourceControl.png "VSIDE_Productivity_SourceControl")

### <a name="extensibility"></a>扩展性

[文档：扩展 Visual Studio](../extensibility/index.md)

Visual Studio 具有一个丰富的扩展生态系统，可在需要时安装或创建扩展。 从*扩展库*或 *Visual Studio Marketplace* 安装扩展，使用 *VS SDK* 生成自己的编辑器插件，或使用 *.NET 编译器平台 SDK* 创建自己的实时代码分析器或重构。 可通过下载 [Microsoft 代码分析](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017)扩展，查找附加代码修复和建议。

![Visual Studio 扩展库](../ide/media/VSIDE_Productivity_Extensibility.png "VSIDE_Productivity_Extensibility")
