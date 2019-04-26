---
title: 如何：将项目配置为面向平台
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- project settings [Visual Studio], targeting platforms
- platforms, targeting specific CPUs
- project properties [Visual Studio], targeting platforms
- projects [Visual Studio], targeting platforms
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- CPUs, targeting specific
- 64-bit applications [Visual Studio]
ms.assetid: 845302fc-273d-4f81-820a-7296ce91bd76
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a014e4210f1c94637564e5db86846ed2ade29468
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438192"
---
# <a name="how-to-configure-projects-to-target-platforms"></a>如何：将项目配置为面向平台

可使用 Visual Studio 将应用程序设置为面向不同平台（包括 64 位平台）。 若要深入了解 Visual Studio 中对 64 位平台的支持，请参阅 [64 位应用程序](/dotnet/framework/64-bit-apps)。

## <a name="target-platforms-with-the-configuration-manager"></a>使用 Configuration Manager 设定目标平台

“配置管理器”提供了一种快速添加面向项目的新平台的方法。 如果选择 Visual Studio 附带的平台之一，则将修改项目属性，以便生成适用于所选平台的项目。

### <a name="to-configure-a-project-to-target-a-64-bit-platform"></a>将项目配置为面向 64 位平台

1. 在菜单栏上，依次选择“生成” > “Configuration Manager”。

2. 在“活动解决方案平台”列表中，选择一个 64 位平台作为解决方案目标，然后选择“关闭”按钮。

    1. 如果所需平台未出现在“活动解决方案平台”列表中，请选择“新建”。

         将显示“新建解决方案平台”对话框。

    2. 在“键入或选择新平台”列表中，选择“x64”。

        > [!NOTE]
        > 如果对配置进行了重命名，则可能需要修改“项目设计器”中的设置，以面向正确的平台。

    3. 如果要复制当前平台配置的设置，请选择它，然后选择“确定”按钮。

面向 64 位平台的所有项目的属性均已更新，并将为 64 位平台优化项目的下一个生成。

## <a name="target-platforms-in-the-project-designer"></a>在项目设计器中设定平台目标

项目设计器还提供使项目面向不同平台的方法。 如果在“新建解决方案平台”对话框的列表中选择的平台之一不适合自己的解决方案，则可以创建自定义配置名称并修改“项目设计器”中的配置以面向正确的平台。

此任务的执行根据所用编程语言而有所不同。 有关详细信息，请参阅以下链接：

- 对于 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 项目，请参阅 [/platform (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform)。

- 对于 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 项目，请参阅[“项目设计器”->“生成”页 (C#)](../ide/reference/build-page-project-designer-csharp.md)。

- 对于 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 项目，请参阅 [/clr（公共语言运行时编译）](/cpp/build/reference/clr-common-language-runtime-compilation)。

## <a name="see-also"></a>请参阅

- [了解生成平台](../ide/understanding-build-platforms.md)
- [/platform（C# 编译器选项）](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option)
- [64 位应用程序](/dotnet/framework/64-bit-apps)
- [Visual Studio IDE 64 位支持](../ide/visual-studio-ide-64-bit-support.md)
