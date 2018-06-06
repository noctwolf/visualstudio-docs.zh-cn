---
title: 在 Visual Studio 中以 .NET Framework 版本为目标
ms.date: 02/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- .NET Framework version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 36599475e743259d8cf09d24172a633b54b09693
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752302"
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>如何：面向 .NET Framework 的某个版本

本文档说明如何在创建项目时以 .NET Framework 版本为目标，以及如何更改现有 Visual Basic、C# 或 Visual F# 项目中的目标版本。

> [!IMPORTANT]
> 有关如何更改 C++ 项目目标版本的信息，请参阅[如何：修改目标框架和平台工具集](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)。

## <a name="to-target-a-version-when-you-create-a-project"></a>创建项目时以某一版本为目标

在创建项目时，可用的 .NET Framework 版本取决于安装的版本，以及“新项目”对话框中所选的模板。

1. 在菜单栏上，依次选择“文件” > “新建” > “项目”。

1. 在已安装模板的列表中，选择要创建的项目类型，然后输入一个项目名称。

1. 从“新建项目”对话框底部的“框架”列表中，选择希望项目作为目标的 .NET Framework 版本。

    “框架”列表仅显示那些适用于所选模板的版本。 某些项目类型（如 .NET Core）不需要 .NET Framework。 在这种情况下，“框架”下拉列表将隐藏。

    ![“新建项目”对话框中的“框架”下拉列表](media/vside-newproject-framework.png)

1. 选择“确定”  按钮。

## <a name="to-change-the-targeted-version"></a>更改目标版本

可以按照以下步骤，更改 Visual Basic、C# 或 Visual F# 项目中的 .NET Framework 目标版本。

有关如何更改 C++ 项目目标版本的信息，请参阅[如何：修改目标框架和平台工具集](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)。

1. 在“解决方案资源管理器”中，打开要更改的项目的快捷菜单，然后选择“属性”。

    ![Visual Studio 解决方案资源管理器属性](../ide/media/vs_slnexplorer_properties.png)

1. 在“属性”窗口的左列中，选择“应用程序”选项卡。

    ![Visual Studio 应用程序属性的“应用程序”选项卡](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > 创建 UWP 应用后，无法更改 Windows 或 .NET Framework 目标版本。

1. 在“目标框架”列表中，选择所需版本。

1. 在显示的“验证”对话框中，选择“是”按钮。

    项目将卸载。 项目重新加载时，将以你刚选择的 .NET Framework 版本为目标。

    > [!NOTE]
    > 如果代码中包含对不同于目标版本的 .NET Framework 版本的引用，则在编译或运行代码时可能会显示错误消息。 若要解决这些错误，必须修改这些引用。 请参阅 [.NET Framework 目标错误疑难解答](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)。

## <a name="see-also"></a>请参阅

- [Visual Studio 多目标概述](../ide/visual-studio-multi-targeting-overview.md)
- [.NET Framework 目标错误疑难解答](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [项目设计器的应用程序页 (C#)](../ide/reference/application-page-project-designer-csharp.md)
- [项目设计器的应用程序页 (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [如何：修改目标框架和平台工具集 (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)