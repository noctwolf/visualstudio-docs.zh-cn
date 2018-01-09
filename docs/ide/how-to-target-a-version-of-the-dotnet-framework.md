---
title: "如何：面向 .NET Framework 的某个版本 | Microsoft Docs"
ms.custom: 
ms.date: 12/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], targeting .NET Framework version
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: f648f07923117b89278ba0e5f44e351b923f7c26
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>如何：面向 .NET Framework 的某个版本

本文档说明如何在创建项目时以 .NET Framework 版本为目标，以及如何更改现有 Visual Basic、Visual C# 或 Visual F# 项目中的目标版本。

> [!IMPORTANT]
> 有关如何更改 C++ 项目目标版本的信息，请参阅[如何：修改目标框架和平台工具集](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)。

## <a name="targeting-a-version-when-you-create-a-project"></a>创建项目时以某一版本为目标

创建项目时，目标 .NET Framework 版本将确定可以使用的模板。

### <a name="to-target-a-version-when-you-create-a-project"></a>创建项目时以某一版本为目标

1.  在菜单栏上，依次选择“文件” 、“新建” 、“项目” 。

2.  在“新建项目”对话框顶部的列表中，选择你希望项目作为目标的 .NET Framework 版本。

3.  在已安装模板的列表中，选择要创建的项目类型，命名项目，然后选择“确定”按钮。

    模板列表仅显示你选择的 .NET Framework 版本支持的项目。

## <a name="changing-the-target-version"></a>更改目标版本

可以按照以下步骤，更改 Visual Basic、Visual C# 或 Visual F# 项目中的 .NET Framework 目标版本。

有关如何更改 C++ 项目目标版本的信息，请参阅[如何：修改目标框架和平台工具集](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)。

### <a name="to-change-the-targeted-version"></a>更改目标版本

1.  在“解决方案资源管理器”中，打开要更改的项目的快捷菜单，然后选择“属性”。

    ![Visual Studio 解决方案资源管理器属性](../ide/media/vs_slnexplorer_properties.png "vs_slnExplorer_Properties")

2. 在“属性”窗口的左列中，选择“应用程序”选项卡。

    ![Visual Studio 应用属性应用程序选项卡](../ide/media/vs_slnexplorer_properties_applicationtab.png "vs_slnExplorer_Properties_ApplicationTab")

    > [!NOTE]
    > 创建 UWP 应用后，无法更改 Windows 或 .NET Framework 目标版本。

3.  在“目标框架”列表中，选择所需版本。

4.  在显示的“验证”对话框中，选择“是”按钮。

    项目将卸载。 项目重新加载时，将以你刚选择的 .NET Framework 版本为目标。

    > [!NOTE]
    > 如果代码中包含对不同于目标版本的 .NET Framework 版本的引用，则在编译或运行代码时可能会显示错误消息。 若要解决这些错误，必须修改这些引用。 请参阅 [.NET Framework 目标错误疑难解答](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)。

## <a name="see-also"></a>请参阅

[Visual Studio 多目标概述](../ide/visual-studio-multi-targeting-overview.md)  
[.NET Framework 目标错误疑难解答](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)  
[“项目设计器”->“应用程序”页 (C#)](../ide/reference/application-page-project-designer-csharp.md)  
[“项目设计器”->“应用程序”页 (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)  
[如何：修改目标框架和平台工具集 (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)