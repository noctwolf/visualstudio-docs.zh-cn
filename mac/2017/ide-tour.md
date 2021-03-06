---
title: Visual Studio for Mac 教程
description: Visual Studio for Mac 提供用于在 macOS 上生成 .NET 应用程序的集成开发环境，包括 ASP.NET Core 网站和适用于 iOS、Android、Mac 和 Xamarin.Forms 的 Xamarin 项目。
author: conceptdev
ms.author: crdun
ms.date: 02/07/2019
ms.assetid: 7DC64A52-AA41-4F3A-A8A1-8A20BCD81CC7
ms.custom: video
ms.openlocfilehash: 43b7918dfba6ff1d8076d3173900ecdc1b1223a3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62998315"
---
# <a name="visual-studio-2017-for-mac-tour"></a>Visual Studio 2017 for Mac 导览

> [!NOTE]
> Visual Studio 2019 for Mac [现已推出](installation.md)。

Visual Studio for Mac 是 Mac 上的 .NET 集成开发环境，可用于编辑、调试和生成代码，然后发布应用。 除了预期的功能（例如，标准编辑器和调试程序）外，Visual Studio for Mac 还包括编译器、代码完成工具、图形设计器和源代码管理，以简化软件开发过程。

Visual Studio for Mac 支持许多与其 Windows 对应的文件类型相同的文件类型（例如 `.csproj`、`.fsproj` 或 `.sln`文件），并且支持 EditorConfig 等功能，这意味着可以使用最适合自己的 IDE。
对于之前使用过 Windows 上的 Visual Studio 人的任何人来说，在创建、打开和开发应用时将不会觉得陌生。 此外，Visual Studio for Mac 采用许多强大的工具，将它的 Windows 对应产品打造成十分强大的 IDE。 Roslyn 编译器平台用于重构和 IntelliSense。 它的项目系统和生成引擎使用 MSBuild，它的源编辑器支持 TextMate 包。 对于 Xamarin 和 .NET Core 应用，使用的是相同的调试器引擎，对于 Xamarin.iOS 和 Xamarin.Android 使用的是相同的设计器。

## <a name="what-can-i-do-in-visual-studio-for-mac"></a>可以在 Visual Studio for Mac 中执行的操作

Visual Studio for Mac 支持以下类型的开发：

- 使用 C#、F# 的 ASP.NET Core Web 应用程序，以及对 Razor 页面、JavaScript 和 TypeScript 的支持
- 使用 C# 或 F# 的 .NET Core 控制台应用程序
- 使用 C# 的跨平台 Unity 游戏和应用程序
- 使用 C# 或 F# 和 XAML 的 Xamarin 中的 Android、iOS、tvOS 和 watchOS 应用程序
- 使用 C# 或 F# 的 Cocoa 桌面应用

本文探讨了 Visual Studio for Mac 的各个部分，并简要介绍了使其成为一款用于创建这些应用程序的强大工具的部分功能。

## <a name="ide-tour"></a>IDE 教程

Visual Studio for Mac 分为多个部分，用于管理应用程序文件和设置、创建应用程序代码以及进行调试。

## <a name="welcome-screen"></a>欢迎屏幕

启动时，Visual Studio for Mac 将显示“欢迎屏幕”：

![欢迎屏幕](media/ide-tour-image1.png)

欢迎屏幕包含以下部分：

- 工具栏 - 提供到搜索栏的快速访问。 加载解决方案时，工具栏用于设置调试和显示错误相关的应用配置。
- 入门 - 为开始使用 Visual Studio for Mac 的开发人员提供到实用主题的快速访问。
- 最新解决方案 - 提供到最近打开的解决方案的快速访问和用于打开或创建项目的便捷按钮。
- 开发人员新闻 - 有助于了解 Microsoft 开发人员的最新信息的新闻源。

## <a name="solutions-and-projects"></a>解决方案和项目

下图显示加载了应用程序的 Visual Studio for Mac：

![加载了应用程序的 Visual Studio for Mac](media/ide-tour-image17.png)

以下部分概述了 Visual Studio for Mac 中的主要区域。

## <a name="solution-pad"></a>Solution Pad

Solution Pad 在解决方案中组织项目：

![在 Solution Pad 中组织的项目](media/ide-tour-image18.png)

在此位置，源代码、资源、用户界面和依赖关系的文件被组织到特定于平台的项目中。

有关在 Visual Studio for Mac 中使用项目和解决方案的详细信息，请参阅[项目和解决方案](/visualstudio/mac/projects-and-solutions)一文。

## <a name="assembly-references"></a>程序集引用

“引用”文件夹中提供每个项目的程序集引用：

![Solution Pad 中的“引用”文件夹](media/ide-tour-image19.png)

使用“编辑引用”对话框添加其他引用，双击“引用”文件夹或在其上下文菜单操作中选择“编辑引用”便可显示该对话框：

![“编辑引用”对话框](media/ide-tour-image20.png)

有关在 Visual Studio for Mac 中使用引用的详细信息，请参阅[管理项目中的引用](/visualstudio/mac/managing-references-in-a-project)一文。

## <a name="dependencies--packages"></a>依赖关系/包

在应用中使用的所有外部依赖关系存储在“依赖关系”或“包”文件夹中，具体取决于所在的项目是 .NET Core 还是 Xamarin.iOS/Xamarin.Android 项目。 通常以 NuGet 的形式提供这些内容。

NuGet 是 .NET 开发最常用的程序包管理器。 通过 Visual Studio 的 NuGet 支持，可以轻松地搜索包并将其添加到项目，再添加到应用程序。

若要将依赖关系添加到应用程序，请右键单击“依赖关系”/“包”文件夹，然后选择“添加包”：

![添加 NuGet 包](media/ide-tour-image21.png)

可在[在项目中包括 NuGet 包](/visualstudio/mac/nuget-walkthrough)一文中找到在应用程序中使用 NuGet 包的相关信息。

## <a name="refactoring"></a>重构

使用 Visual Studio for Mac，可通过以下两种实用方法来重构代码：上下文操作和源分析。 可在[重构](/visualstudio/mac/refactoring)一文中阅读更多相关信息。

## <a name="debugging"></a>调试

Visual Studio for Mac 具有本机调试器，支持 Xamarin.iOS、Xamarin.Mac 和 Xamarin.Android 应用程序的调试。 Visual Studio for Mac 使用 Mono 软调试器，该调试器在 Mono 运行时中实施，以便 IDE 跨所有平台调试托管代码。 有关调试的其他信息，请访问[调试](/visualstudio/mac/debugging)一文。

调试器包含丰富的可视化工具，可用于字符串、颜色、URL、大小、坐标和贝塞尔曲线等特殊类型。

有关调试器的数据可视化效果的详细信息，请访问[数据可视化效果](/visualstudio/mac/data-visualizations)一文。

## <a name="version-control"></a>版本控制

Visual Studio for Mac 与 Git 和 Subversion 源控件系统集成。 源控件下的项目用解决方案名称旁列出的分支表示：

![分支名称用来表示源控件下的项目](media/ide-tour-image22.png)

如果文件有未提交的更改，文件在解决方案窗格中的图标上就会有注释，如下图所示：

![Solution Pad 中的未提交文件](media/ide-tour-image23.png)

有关在 Visual Studio 中使用版本控制的详细信息，请参阅[版本控制](/visualstudio/mac/version-control)一文。

## <a name="related-video"></a>相关视频

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Overview/player]

## <a name="see-also"></a>请参阅

- [Visual Studio IDE (Windows)](/visualstudio/ide/visual-studio-ide)
