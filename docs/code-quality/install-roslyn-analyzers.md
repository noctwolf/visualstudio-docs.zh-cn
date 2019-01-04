---
title: 安装 Roslyn 分析器
ms.date: 08/03/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: d828fbf2bce435c067b6bc1cc66ce379f3304988
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53929453"
---
# <a name="install-net-compiler-platform-analyzers"></a>安装.NET Compiler Platform 分析器

Visual Studio 2017 包括一组核心.NET 编译器平台 (*Roslyn*) 分析器。 这些分析器将始终启用。 你可以安装其他分析器作为 NuGet 包，或在 Visual Studio 扩展*VSIX*文件。

## <a name="to-install-nuget-analyzer-packages"></a>若要安装 NuGet 分析器包

1. 找到你想要在 www.nuget.org 安装分析器包。例如，您可能希望[安装 Microsoft FxCop 分析器](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-nuget-package)检查有关安全性和性能问题，以及其他代码。

2. 在 Visual Studio 中，使用安装包[程序包管理器控制台](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console)或[包管理器 UI](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console)。

   > [!NOTE]
   > 对于每个分析器包 www.nuget.org 页显示您要粘贴的命令**程序包管理器控制台**。 甚至还有一个方便的按钮文本复制到剪贴板。
   > 
   > ![NuGet.org 页面显示包管理器控制台命令](media/nuget-install-command.png)

   分析器程序集安装并显示在**解决方案资源管理器**下**引用** > **分析器**。

## <a name="to-install-vsix-analyzers"></a>若要安装 VSIX 分析器

1. 在 Visual Studio 中，选择**工具** > **扩展和更新**。

   此时，“扩展和更新”对话框打开。

   > [!NOTE]
   > 或者，可以查找并下载分析器扩展直接从[Visual Studio Marketplace](https://marketplace.visualstudio.com)。

2. 展开**联机**在左窗格中，然后选择**Visual Studio Marketplace**。

3. 在搜索框中，键入你想要安装分析器扩展插件的名称。 例如，您可能希望[安装 Microsoft FxCop 分析器](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-vsix)检查有关安全性和性能问题，以及其他代码。

4. 选择**下载**。

   下载此扩展。

5. 选择**确定**以关闭对话框，然后关闭 Visual Studio 启动的所有实例**VSIX 安装程序**。

   **VSIX 安装程序**对话框随即打开。

   ![VSIX 安装程序以进行 Microsoft 代码分析](media/vsix-installer-code-analysis.png)

6. 选择**修改**以开始安装。

7. 后一分钟或两个，安装完成。 选择**关闭**。

8. Visual Studio 中再次打开。

如果你想要检查扩展是否已安装，选择**工具** > **扩展和更新**。 在**扩展和更新**对话框中，选择**已安装**左边的类别，然后按名称搜索该扩展。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [在 Visual Studio 中使用 Roslyn 分析器](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中的 Roslyn 分析器的概述](../code-quality/roslyn-analyzers-overview.md)
- [安装 FxCop 分析器](../code-quality/install-fxcop-analyzers.md)