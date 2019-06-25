---
title: 面向 .NET 版本
ms.date: 03/21/2019
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET [Visual Studio]
- .NET version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2c316610fc007e3e8642567c01a5172feb461bda
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747126"
---
# <a name="how-to-target-a-version-of-net"></a>如何：面向 .NET 版本

本文介绍在创建 .NET Framework 项目如何面向 .NET Framework 的特定版本。 还介绍如何在现有的 Visual Basic、C# 或 F# 项目中更改目标版本。

> [!IMPORTANT]
> 有关如何更改 C++ 项目的目标版本的信息，请参阅[如何：修改目标框架和平台工具集](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)。

## <a name="target-a-version-when-you-create-a-project"></a>创建项目时以某一版本为目标

创建 .NET Framework 项目时，可用的 .NET Framework 版本取决于安装的版本，以及所选的项目模板。

1. 在菜单栏上，依次选择“文件”   > “新建”   > “项目”  。

1. 为要创建的项目类型选择一个 .NET Framework 模板。

1. 从对话框底部的“框架”下拉列表中，选择希望项目面向的 .NET Framework 版本  。

   “框架”列表仅显示那些适用于所选模板的版本。

   > [!NOTE]
   > 某些项目类型（如 .NET Core）不会显示“框架”下拉列表  。

   ::: moniker range="vs-2017"

   ![Visual Studio 2017“新建项目”对话框中的“框架”下拉列表](media/vside-newproject-framework.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![VS 2019 中的框架选择器](media/vs-2019/configure-new-project-framework.png)

   ::: moniker-end

1. 继续[创建项目](create-new-project.md)。

## <a name="change-the-targeted-version"></a>更改目标版本

可以按照以下步骤，更改 Visual Basic、C# 或 F# 项目中的 .NET 目标版本。

1. 在“解决方案资源管理器”  中，打开要更改的项目的快捷菜单，然后选择“属性”  。

    ![Visual Studio 解决方案资源管理器属性](../ide/media/vs_slnexplorer_properties.png)

1. 在“属性”窗口的左列中，选择“应用程序”选项卡   。

    ![Visual Studio 应用程序属性的“应用程序”选项卡](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > 创建 UWP 应用后，无法更改 Windows 或 .NET 目标版本。

1. 在“目标框架”  列表中，选择所需版本。

1. 在显示的“验证”对话框中，选择“是”  按钮。

    项目将卸载。 项目重载时，将面向刚选择的 .NET 版本。

    > [!NOTE]
    > 如果代码中包含对非目标 .NET 版本的引用，则在编译或运行代码时可能会显示错误消息。 若要解决这些错误，必须修改这些引用。 请参阅 [.NET 定位错误疑难解答](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)。

## <a name="see-also"></a>请参阅

- [框架定位概述](../ide/visual-studio-multi-targeting-overview.md)
- [.NET Framework 目标错误疑难解答](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [项目设计器的应用程序页 (C#)](../ide/reference/application-page-project-designer-csharp.md)
- [项目设计器的应用程序页 (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [如何：修改目标框架和平台工具集 (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)