---
title: 设置调试和发布配置 |Microsoft Docs
ms.custom: ''
ms.date: 10/05/2018
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.builds
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- configurations, release
- build configurations, release
- projects [Visual Studio], release configurations
- debugging [Visual Studio], release configurations
- release builds, changing settings
- debug builds
- debug builds, switching to release build
- debug builds, changing configuration settings
- debugging [Visual Studio], debug configurations
- projects [Visual Studio], debug configurations
- build configurations, debug
- debug configurations
- release builds, switching to debug build
- Visual Basic projects, debug and release builds
ms.assetid: 57b6bbb7-f2af-48f7-8773-127d75034ed2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9a65a3331c210bdfb4143ff890180fdc7d663229
ms.sourcegitcommit: a7de99f36e9ead7ea9e9bac23c88d05ddfc38b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2018
ms.locfileid: "52257220"
---
# <a name="set-debug-and-release-configurations-in-visual-studio"></a>设置调试和发布 Visual Studio 中的配置

Visual Studio 项目具有针对你的程序的单独发布和调试配置。 生成用于调试的调试版本和最终发布分发的版本。

在调试配置中，您的程序将编译使用完整符号调试信息，不进行优化。 优化会使调试复杂化，因为源代码和生成的指令之间的关系更加复杂。

您的程序的发布配置具有任何符号调试信息进行了完全优化。 调试信息可以生成.pdb 文件中[具体取决于编译器选项](#BKMK_symbols_release)的使用。 创建.pdb 文件可能很有用，如果您稍后必须调试发行版本。

有关生成配置的详细信息，请参阅[了解生成配置](../ide/understanding-build-configurations.md)。

你可以将生成配置从**生成**菜单中的，从工具栏中，或在项目属性页。 项目属性页是特定于语言的。 下面的过程演示如何从菜单和工具栏更改生成配置。 有关如何更改中采用不同语言的项目的生成配置的详细信息，请参阅[另请参阅](#see-also)下面一节。

## <a name="change-the-build-configuration"></a>更改生成配置

若要更改生成配置，可以：

* 从**构建**菜单中，选择**Configuration Manager**，然后选择**调试**或者**版本**。

或

* 在工具栏中，选择**调试**或**发行**从**解决方案配置**列表。

  ![工具栏生成配置](../debugger/media/toolbarbuildconfiguration.png "ToolbarBuildConfiguration")

## <a name="BKMK_symbols_release"></a>生成符号 (.pdb) 文件 (C#，c + +、 Visual Basic 中， F#)

您可以选择生成符号 (.pdb) 文件以及调试要包含的信息。 对于大多数项目类型，编译器将生成默认情况下调试的符号文件和发布版本，而其他默认设置因项目类型和 Visual Studio 版本而异。

> [!IMPORTANT]
> 调试器只会为可执行文件加载与该可执行文件生成之时所创建的 .pdb 文件完全匹配的 .pdb 文件（即该 .pdb 文件必须是原始 .pdb 文件或其副本）。 有关详细信息，请参阅[为什么 Visual Studio 要求调试器符号文件完全匹配与同时生成的二进制文件？](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)

每个项目类型可能具有不同的方式设置这些选项。

### <a name="generate-symbol-files-for-a-c-aspnet-or-visual-basic-project"></a>生成 C#、 ASP.NET 或 Visual Basic 项目的符号文件

在 C# 或 Visual Basic 调试配置的项目设置的详细信息，请参阅[调试配置适用于 C# 项目设置](../debugger/project-settings-for-csharp-debug-configurations.md)或[项目设置适用于 Visual Basic 调试配置](../debugger/project-settings-for-a-visual-basic-debug-configuration.md).

1. 在“解决方案资源管理器”中，选择项目。

2. 选择**属性**图标 (或按**Alt + Enter**)。

3. 在侧窗格中，选择**构建**(或**编译**在 Visual Basic 中)。

4. 在中**配置**列表中，选择**调试**或**发行**。

5. 选择**高级**按钮 (或**高级编译选项**在 Visual Basic 中的按钮)。

6. 在中**调试信息**列表 (或**生成调试信息**在 Visual Basic 中的列表)，选择**完整**， **pdb**，或**可移植**。

   可移植的格式是为.NET Core 的最新的跨平台格式。 有关选项的详细信息，请参阅[高级生成设置对话框 (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md)。

   ![在 C# 中生成的生成 Pdb](../debugger/media/dbg_project_properties_pdb_csharp.png "GeneratePDBsForCSharp")

7. 生成你的项目。

   编译器在可执行文件或主输出文件所在的文件夹中创建的符号文件。

### <a name="generate-symbol-files-for-a-c-project"></a>生成 c + + 项目的符号文件

1. 在“解决方案资源管理器”中，选择项目。

2. 选择**属性**图标 (或按**Alt + Enter**)。

3. 在中**配置**列表中，选择**调试**或**发行**。

4. 在侧窗格中，选择**链接器 > 调试**，然后选择选项**生成调试信息**。

   在 c + + 调试配置的项目设置的详细信息，请参阅[调试配置的 c + + 项目设置](../debugger/project-settings-for-a-cpp-debug-configuration.md)。

5. 配置选项**生成程序数据库文件**。

   在大多数 c + + 项目中，默认值是`$(OutDir)$(TargetName).pdb`，其中的输出文件夹中生成.pdb 文件。

   ![C + + 中生成的生成 Pdb](../debugger/media/dbg_project_properties_pdb_cplusplus.png "GeneratePDBsforCPlusPlus")

6. 生成你的项目。

   编译器在可执行文件或主输出文件所在的文件夹中创建的符号文件。

## <a name="see-also"></a>另请参阅
 
[在 Visual Studio 调试器中指定符号 (.pdb) 文件和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)<br/>
[调试器设置和准备](../debugger/debugger-settings-and-preparation.md)<br/>
[C++ 调试配置的项目设置](../debugger/project-settings-for-a-cpp-debug-configuration.md)<br/>
[C# 调试配置的项目设置](../debugger/project-settings-for-csharp-debug-configurations.md)<br/>
[Visual Basic 调试配置的项目设置](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)<br/>
[如何：创建和编辑配置](../ide/how-to-create-and-edit-configurations.md)
