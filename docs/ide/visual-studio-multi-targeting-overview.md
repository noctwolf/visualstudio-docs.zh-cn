---
title: 面向 .NET Framework
ms.date: 02/06/2018
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- multi-targeting [Visual Studio]
- multitargeting [Visual Studio]
- framework targeting [Visual Studio]
- .NET framework targeting [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 451464cd2576c1dd70c7b8235cead327b2f05ca2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62582107"
---
# <a name="visual-studio-multi-targeting-overview"></a>Visual Studio 多目标概述

在 Visual Studio 中，可以指定希望项目面向的 .NET Framework 的版本或配置文件。 对于在另一台计算机上运行的应用程序，应用程序面向的 Framework 版本必须与计算机上安装的 Framework 版本兼容。

还可以创建包含面向不同版本框架的项目的解决方案。 框架目标有助于确保应用程序仅使用指定的框架版本中可用的功能。

> [!TIP]
> 你还可以针对不同平台确定目标应用程序。 有关详细信息，请参阅[多定向](../msbuild/msbuild-multitargeting-overview.md)。

## <a name="framework-targeting-features"></a>框架目标功能

框架目标包含下列功能：

- 打开针对 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 早期版本的项目时，Visual Studio 可自动升级项目或者保持目标不变。

- 创建项目时，可指定要面向的 .NET Framework 版本。

- 可更改被现有项目面向的 .NET Framework 的版本。

- 在同一解决方案的各项目中可以面向不同的 .NET Framework 版本。

- 更改项目面向的 .NET Framework 版本时，[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 会对引用和配置文件进行任何所需的更改。

处理针对 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 早期版本的项目时，Visual Studio 会对开发环境进行如下动态更改：

- 它筛选“添加新项”对话框、“添加新引用”对话框和“添加服务引用”对话框中的项，以忽略在目标版本中不可用的选项。

- 在“工具箱”中筛选自定义控件，以删除在目标版本中不可用的控件，并在多个控件可用时仅显示最新版本。

- 对 IntelliSense 进行筛选，忽略在目标版本中不可用的语言功能。

- 筛选“属性”窗口中的属性，以忽略在目标版本中不可用的属性。

- 筛选菜单选项以忽略在目标版本中不可用的选项。

- 对于生成，Visual Studio 使用适用于目标版本的编译器版本和编译器选项。

> [!NOTE]
> 框架目标不保证应用程序可正常运行。 必须对应用程序进行测试，以确保其能够针对目标版本运行。 无法面向版本早于 .NET Framework 2.0 的 Framework。

## <a name="select-a-target-framework-version"></a>选择目标框架版本

创建项目时，请在选择项目模板后，选择目标 .NET Framework 版本。 可用框架的列表包含适用于所选模板类型的已安装框架版本。 对于不需要使用 .NET Framework 的模板类型（例如，.NET Core 模板），“框架”下拉列表将隐藏。

::: moniker range="vs-2017"

![VS 2017 中的“框架”下拉列表](media/vside-newproject-framework.png)

::: moniker-end

::: moniker range=">=vs-2019"

![VS 2019 中的“框架”下拉列表](media/vs-2019/configure-new-project-framework.png)

::: moniker-end

对于现有项目，可在项目属性对话框中更改目标 .NET Framework 版本。 有关详细信息，请参阅[如何：面向 .NET Framework 的某个版本](../ide/how-to-target-a-version-of-the-dotnet-framework.md)。

## <a name="resolve-system-and-user-assembly-references"></a>解析系统和用户程序集引用

若要以 .NET Framework 版本为目标，必须先安装相应的程序集引用。 可以在 [.NET 下载](https://www.microsoft.com/net/download/windows)页下载针对不同版本 .NET Framework 的开发人员包。

“添加引用”对话框禁用了不适合目标 .NET Framework 版本的系统程序集，以免无意中将它们添加到项目。 （系统程序集是包含在 .NET Framework 版本内的 .dll 文件。）若引用所属的框架版本低于目标版本，则无法解析引用，并且无法添加基于此类引用的控件。 若要启用此类引用，请将项目的 .NET Framework 目标重新设置为包含此引用。  有关详细信息，请参阅[如何：面向 .NET Framework 的某个版本](../ide/how-to-target-a-version-of-the-dotnet-framework.md)。

有关程序集引用的详细信息，请参阅[在设计时解析程序集](../msbuild/resolving-assemblies-at-design-time.md)。

## <a name="enable-linq"></a>启用 LINQ

当面向 .NET Framework 3.5 或更高版本时，会自动添加对 System.Core 的引用和 <xref:System.Linq> 的项目级导入（仅 Visual Basic 中）。 若要使用 LINQ 功能，还必须打开 `Option Infer`（仅 Visual Basic 中）。 如果将目标更改为早期的 .NET Framework 版本，将自动删除相关引用和导入。 有关详细信息，请参阅[使用 LINQ](/dotnet/csharp/tutorials/working-with-linq)。

## <a name="see-also"></a>请参阅

- [多目标 (MSBuild)](../msbuild/msbuild-multitargeting-overview.md)
- [如何：修改目标框架和平台工具集 (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)