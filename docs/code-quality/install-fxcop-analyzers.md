---
title: 安装 FxCop 分析器
ms.date: 08/03/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- fxcop analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: be213d25ca406a8532f00ad88b006c36d369e1a9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53893773"
---
# <a name="install-fxcop-analyzers-in-visual-studio"></a>在 Visual Studio 中安装 FxCop 分析器

Microsoft 创建了一组调用的分析器[Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers)，包含静态代码分析，转换为 Roslyn 分析器中的最重要"FxCop"规则。 这些分析器检查您的代码安全、 性能和设计问题，等等。

您可以安装这些 FxCop 分析器，NuGet 包的形式或作为 VSIX 扩展到 Visual Studio。 若要了解有关每个的优缺点，请参阅[NuGet 包 vs。VSIX 扩展](roslyn-analyzers-overview.md#nuget-package-versus-vsix-extension)。

## <a name="to-install-fxcop-analyzers-as-a-nuget-package"></a>若要安装 FxCop 分析器作为 NuGet 包

1. [确定分析器包版本](#fxcopanalyzers-package-versions)若要安装，根据你的 Visual Studio 版本。

2. 在 Visual Studio 中，使用安装包[程序包管理器控制台](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console)或[包管理器 UI](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console)。

   > [!NOTE]
   > 对于每个分析器包的 nuget.org 页显示要粘贴的命令**程序包管理器控制台**。 甚至还有一个方便的按钮文本复制到剪贴板。
   >
   > ![NuGet.org 页面显示包管理器控制台命令](media/nuget-package-manager-command.png)

   分析器程序集已安装，并且它们出现在**解决方案资源管理器**下**引用** > **分析器**。

   ![在解决方案资源管理器中的分析器节点](media/solution-explorer-analyzers-node.png)

### <a name="fxcopanalyzers-package-versions"></a>FxCopAnalyzers 包版本

使用以下准则来确定要安装适用于你的 Visual Studio 版本的 FxCop 分析器包的版本：

| Visual Studio 版本 | FxCop 分析器包版本 |
| - | - |
| Visual Studio 2017 版本 15.5 及更高版本 | 2.6.2 例如 https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.2 |
| Visual Studio 2017 版本 15.3 到 15.4 | 2.3.0-beta1 例如 https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.3.0-beta1 |
| Visual Studio 2017 版本 15.0 到 15.2 | 2.0.0-beta2 例如 https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.0.0-beta2 |
| Visual Studio 2015 更新 2 和 3 | 版本 1.2.0-beta2 例如 https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.2.0-beta2 |
| Visual Studio 2015 Update 1 | 版本 1.1.0，例如 https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.1。 |
| Visual Studio 2015 RTW | 版本 1.0.1 例如 https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.0.1 |

## <a name="to-install-fxcop-analyzers-as-a-vsix"></a>若要为 VSIX 安装 FxCop 分析器

在 Visual Studio 2017 版本 15.5 及更高版本中，可以安装[Microsoft 代码分析 2017年](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017)包含所有托管项目的 FxCop 分析器的扩展。

1. 在 Visual Studio 中，选择**工具** > **扩展和更新**。

   此时，“扩展和更新”对话框打开。

   > [!NOTE]
   > 或者，下载适用的扩展直接从[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017)。

1. 展开**联机**在左窗格中，然后选择**Visual Studio Marketplace**。

1. 在搜索框中，键入"代码分析"，并查找**Microsoft 代码分析 2017年**扩展。

   ![Microsoft 代码分析扩展](media/extensions-and-updates-code-analysis.png)

1. 选择**下载**。

   下载此扩展。

1. 选择**确定**以关闭对话框，然后关闭 Visual Studio 启动的所有实例**VSIX 安装程序**。

   **VSIX 安装程序**对话框随即打开。

   ![VSIX 安装程序以进行 Microsoft 代码分析](media/vsix-installer-code-analysis.png)

1. 选择**修改**以开始安装。

1. 后一分钟或两个，安装完成。 选择**关闭**。

1. Visual Studio 中再次打开。

如果你想要检查扩展是否已安装，选择**工具** > **扩展和更新**。 在**扩展和更新**对话框中，选择**已安装**左边的类别，然后按名称搜索该扩展。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中的 Roslyn 分析器的概述](../code-quality/roslyn-analyzers-overview.md)
- [在 Visual Studio 中使用 Roslyn 分析器](../code-quality/use-roslyn-analyzers.md)
- [从 FxCop 迁移到 Roslyn 分析器](../code-quality/fxcop-analyzers.yml)