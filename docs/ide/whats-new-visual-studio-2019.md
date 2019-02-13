---
title: Visual Studio 2019 中的新增功能
titleSuffix: ''
description: 了解 Visual Studio 2019 中的新增功能。
ms.date: 01/29/2019
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 00bec66b-bcee-46f5-91d9-f73a2b469744
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-dev16
ms.topic: conceptual
ms.workload:
- multiple
monikerRange: '>= vs-2017'
ms.openlocfilehash: 88fe1f9a4f1f3d1d21af2d7d00dee677cab11fc5
ms.sourcegitcommit: e3d96b20381916bf4772f9db52b22275763bb603
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2019
ms.locfileid: "55483700"
---
# <a name="whats-new-in-visual-studio-2019-preview"></a>Visual Studio 2019 预览版中的新增功能

更新了 [预览版 2 版本](/visualstudio/releases/2019/release-notes-preview?context=visualstudio/default&contextView=vs-2017)

>[!div class="button"]
>[下载预览版](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+preview)

Visual Studio 2019 预览版包含许多常规改进以及可优化开发者生产力和团队协作的新功能。 无论是第一次使用 Visual Studio 还是老用户 &mdash; 从简化的项目创建和代码运行状况管理，到团队和开源协作工作流程，你都将能够利用其功能来开发生命周期的所有方面。<br/><br/>

>[!VIDEO https://channel9.msdn.com/Events/Connect/Microsoft-Connect--2018/D190/player]

以下是 Visual Studio 提供的高级扼要重述：

* **[个人和团队生产力](#personal-and-team-productivity)**。 最重要是的每个人的生产力。
* **[新式发展支持](#modern-development-support)**。 支持你当前的项目和未来的解决方案。
* **[持续创新](#continuous-innovation)**。 智慧与智能、云支持的代码。

> [!NOTE]
> 有关 Visual Studio 2019 预览版中新增功能的完整列表，请参阅[发行说明](/visualstudio/releases/2019/release-notes-preview?context=visualstudio/default&contextView=vs-2017)。 要概要了解我们第二个预览版中的新增功能，请参阅[现已推出 Visual Studio 2019 预览版 2](https://blogs.msdn.microsoft.com/visualstudio/2019/01/24/visual-studio-2019-preview-2-is-now-available/) 博客文章。

## <a name="personal-and-team-productivity"></a>个人和团队生产力

在每个 Visual Studio 版本中，性能改进都是首要考虑因素，但随之而来的是提高你的生产力。 以下是我们可以提供的帮助。

### <a name="new-start-window"></a>新的启动窗口

打开 Visual Studio 2019 时，首先映入眼帘的是一个新的启动窗口。

   ![Visual Studio 2019 中的新启动窗口](media/start-window.png)

该新的启动窗口包含以下选项：克隆或签出代码、打开项目或解决方案、打开本地文件夹或创建新项目。 这些选项以简单的对话框形式显示，有助于初学者和高级 Visual Studio 用户快速编写代码。

有关详细信息，请参阅博客文章 [Get to code:How we designed the new Visual Studio start window](https://blogs.msdn.microsoft.com/visualstudio/2018/12/13/get-to-code-how-we-designed-the-new-visual-studio-start-window/)（开始编码：如何设计新的 Visual Studio 开始窗口）。

### <a name="better-search"></a>更好的搜索

（以前称为快速启动）我们的新搜索体验更快、更有效。 现在，搜索结果会在键入时动态显示。 并且，搜索结果包括命令的键盘快捷方式，更便于记忆以备将来使用。

   ![Visual Studio 2019 中的新搜索功能](media/search-feature.png)

无论你是在寻找命令、设置、文档还是其他有用的操作，新的搜索功能都可以让你更轻松地找到所需内容。

### <a name="one-click-code-cleanup"></a>一键代码清除

与新文档运行状况指示符配对是一种新的代码清理命令。 可以使用此新命令通过单击按钮来识别并修复警告和建议。

   ![Visual Studio 2019 中的新代码清理功能](media/code-cleanup.png)

清理将格式化代码并应用[当前设置](code-styles-and-quick-actions.md) [.editorconfig 文件](create-portable-custom-editor-options.md)或 [Roslyn 分析器](../code-quality/roslyn-analyzers-overview.md)建议的任何代码修复程序。

### <a name="debugger-improvements"></a>调试器改进

#### <a name="search-within-a-watch-window-and-format-watch-values"></a>在监视窗口中搜索，并设置监视值的格式

你可能曾经体验过在监视窗口中查找一组值中的字符串。 在 Visual Studio 2019 预览版中，我们在监视、局部变量和自动窗口中添加了搜索，以帮助你查找要查找的对象和值。

还可以格式化监视、本地和自动窗口中值的显示方式。  双击任何窗口中的一个项目并添加逗号 (",") 以访问可能的格式说明符下拉列表，每个列表都包含其预期效果的说明。

   ![Visual Studio 2019 中的新监视窗口和格式化值的功能](media/search-watch-window.png)

有关详细信息，请参阅 [Visual Studio 2019 中的增强功能：在 Watch、Autos、Locals 窗口中搜索对象和属性](https://blogs.msdn.microsoft.com/visualstudio/2019/01/28/enhanced-in-visual-studio-2019-search-for-objects-and-properties-in-the-watch-autos-and-locals-windows/)博客文章。

### <a name="visual-studio-live-share"></a>Visual Studio Live Share

[Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/) 是一项开发者服务，可让你与团队成员共享代码库及其上下文，并直接从 Visual Studio 内获得即时双向协作。 利用“实时共享”，团队成员可以无缝且安全地读取、导航、编辑和调试已与他们共享的项目。

Visual Studio 2019 预览版中会默认安装此服务。

有关详细信息，请参见博客文章 [Visual Studio Live Share for real-time code reviews and interactive education](https://blogs.msdn.microsoft.com/visualstudio/2018/12/06/visual-studio-live-share-for-real-time-code-reviews-and-interactive-education/)（用于实时代码评审和交互式教育的 Visual Studio Live Share）。

## <a name="modern-development-support"></a>新式开发支持

### <a name="manage-pull-requests-prs-from-the-ide"></a>管理来自 IDE 的拉取请求 (PR)

我们正在推出一个新的扩展，你可以下载该扩展与 Visual Studio 2019 预览版一起使用。 使用此新扩展，可以查看、运行甚至调试团队的拉取请求，而无需离开 Visual Studio IDE[（集成开发环境）](../get-started/visual-studio-ide.md)。 我们目前支持 Azure Repos 中的代码，但正在扩展以支持 GitHub 并改善整体体验。

要立即开始使用，可从 Visual Studio Marketplace 下载 [Visual Studio 的拉取请求](https://aka.ms/pr4vs)扩展。

### <a name="develop-with-net-core-3-preview-1"></a>使用 .NET Core 3 预览版 1 进行开发

Visual Studio 2019 的预览版支持构建适用于任何平台的 [.NET Core 3](http://aka.ms/netcore3preview1) 应用程序。 我们将继续支持和改进跨平台的 C++ 开发，以及 iOS 的 .NET 移动开发和 Android 的 Xamarin 开发。

   ![使用 Visual Studio 2019 中的 .NET Core 3 预览版 1 开发应用](media/dot-net-core-three-dev.png)

## <a name="continuous-innovation"></a>持续创新

### <a name="per-monitor-aware-pma-rendering"></a>按监视器感知 (PMA) 呈现

如果使用配置了不同显示比例因子的监视器，或远程连接到显示比例因子与主设备不同的计算机，你可能会发现 Visual Studio 看起来比较模糊或以错误的比例呈现。

随着 Visual Studio 2019 预览版的发布，我们正在采取初步措施让 Visual Studio 成为一种按监视器感知 (PMA) 应用程序。 我们正在努力构建基础工作，确保无论使用何种显示比例因子，Visual Studio 都能正确呈现。

   ![Visual Studio 2019 中的按监视器感知 (PMA) 呈现](media/per-monitor-aware-dpi-scaling.png)

### <a name="visual-studio-intellicode"></a>Visual Studio IntelliCode

[Visual Studio IntelliCode](/visualstudio/intellicode/) 是一种扩展，可通过使用人工智能 (AI) 来增强软件开发工作。 IntelliCode 将在 GitHub 上训练 2,000 个开源项目（每个项目包含 100 个星级）以生成这些建议。

下面是 Visual Studio IntelliCode 帮助提高生产力的几种方法：

* 提供上下文感知代码完成
* 指导开发人员遵守团队的模式和样式
* 发现难以察觉的代码问题
* 将关注点集中到重要领域，从而专注代码评审

我们在适用于 Visual Studio 的 IntelliCode 扩展预览版中最初仅支持 C#。 现在，我们添加了对 Visual Studio 中 C++ 和 XAML 的支持。

如果你使用的是 C#，我们还添加了在你自己的代码上训练自定义模型的功能。

有关最近的更新的详细信息，请参阅博客文章 [Visual Studio IntelliCode supports more languages and learns from your code](https://blogs.msdn.microsoft.com/visualstudio/2018/12/05/visual-studio-intellicode-supports-more-languages-and-learns-from-your-code/)（Visual Studio IntelliCode 可支持更多语言并学习你的代码）。 而且，有关扩展和如何下载扩展的详细信息，请参阅 Microsoft DevLabs 上的 [Visual Studio IntelliCode - Preview](https://go.microsoft.com/fwlink/?linkid=872707)（Visual Studio IntelliCode - 预览版）页面。

## <a name="give-us-feedback"></a>给我们提供反馈

为什么将反馈发送至 Visual Studio 团队？ 因为我们严肃对待客户反馈。 这会给予我们巨大的行事动力。

* 如果想对如何改进 Visual Studio 提出建议，可以使用[提供建议](talk-to-us.md#i-want-to-make-a-suggestion-about-visual-studio-features)工具。

* 如果遇到挂起、崩溃或其他性能问题，可利用[报告问题](talk-to-us.md#i-want-to-report-a-problem-with-visual-studio)工具与我们轻松共享重现步骤和支持文件。

## <a name="see-also"></a>请参阅

* [Visual Studio 2019 发行说明](/visualstudio/releases/2019/release-notes-preview?context=visualstudio/default&contextView=vs-2017)
* [Microsoft Connect()；2018 会议](https://www.microsoft.com/connectevent)
* [Visual Studio 2017 中的新增功能](whats-new-visual-studio-2017.md)
