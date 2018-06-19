---
title: 在 Visual Studio 中安装 Roslyn 分析器
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: fb2f681de16a53c97954c8c37b8dd28b163998ee
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31927528"
---
# <a name="install-net-compiler-platform-analyzers"></a>安装.NET Compiler Platform 分析器

Visual Studio 2017 包括一组核心的.NET Compiler Platform (*Roslyn*) 分析器。 这些分析器将始终位于中。 你可以为 NuGet 包，或作为 Visual Studio 中的扩展安装其他分析器*VSIX*文件。

## <a name="to-install-nuget-package-analyzers"></a>若要安装 NuGet 包分析器

1. [确定的分析器程序包版本](https://github.com/dotnet/roslyn-analyzers#recommended-version-of-analyzer-packages)若要安装，根据你的 Visual Studio 版本。

1. 在 Visual Studio 中，使用安装包[程序包管理器控制台](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console)或[包管理器 UI](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console)。

   > [!NOTE]
   > 对于每个分析器程序包的 nuget.org 页显示要粘贴的命令**程序包管理器控制台**。 即使是一个方便的按钮，以将文本复制到剪贴板。
   >
   > ![显示程序包管理器控制台命令的 NuGet.org 页](media/nuget-package-manager-command.png)

   分析器程序集安装并显示在**解决方案资源管理器**下**引用** > **分析器**。

   ![在解决方案资源管理器的分析器节点](media/solution-explorer-analyzers-node.png)

## <a name="to-install-vsix-analyzers"></a>若要安装 VSIX 分析器

1. 在 Visual Studio 中，选择**工具** > **扩展和更新**。

   此时，“扩展和更新”对话框打开。

   > [!NOTE]
   > 或者，下载直接从扩展[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017)。

1. 展开**联机**在左窗格中，，然后选择**Visual Studio Marketplace**。

1. 在搜索框中，键入"代码分析"，并查找**Microsoft 代码分析 2017年**扩展。

   ![Microsoft 代码分析扩展](media/extensions-and-updates-code-analysis.png)

1. 选择**下载**。

   下载该扩展。

1. 选择**确定**以关闭对话框，然后关闭 Visual Studio 启动的所有实例**VSIX Installer**。

   **VSIX Installer**对话框随即打开。

   ![VSIX 安装程序以进行 Microsoft 代码分析](media/vsix-installer-code-analysis.png)

1. 选择**修改**开始安装。

1. 在一分钟后两个，安装完成。 选择**关闭**。

1. 再次打开 Visual Studio。

如果你想要检查扩展是否已安装，选择**工具** > **扩展和更新**。 在**扩展和更新**对话框中，选择**已安装**类别在左侧，然后按名称搜索扩展。

## <a name="next-steps"></a>后续步骤

- [使用 Visual Studio 中的 Roslyn 分析器](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>请参阅

- [Roslyn 分析器在 Visual Studio 中的概述](../code-quality/roslyn-analyzers-overview.md)