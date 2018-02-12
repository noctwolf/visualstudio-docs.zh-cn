---
title: "在 Azure 虚拟机上使用 Visual Studio | Microsoft Docs"
description: "了解如何在 Azure 虚拟机上使用 Visual Studio"
ms.date: 01/30/2018
ms.technology: vs-acquisition
ms.topic: article
helpviewer_keywords:
- azure services
- virtual machine; VM
- installation
- visual studio
author: PhilLee-MSFT
ms.author: phillee
manager: sacalla
ms.workload:
- multiple
ms.openlocfilehash: d8e99965867d5dbc2710d6c56c5b3dc90fc16dc8
ms.sourcegitcommit: 4b4027244b8de25e30b533148804b87321d3e8a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a id="top"> </a> Azure 上的 Visual Studio 映像
使用在预配置的 Azure 虚拟机 (VM) 中运行的 Visual Studio 是从零构建开发环境的最简单快速的方法。  [Azure Marketplace](https://portal.azure.com/) 中提供了具有不同 Visual Studio 配置的系统映像。 只需启动 VM 即可。

初次使用 Azure？ [创建免费的 Azure 帐户](https://azure.microsoft.com/free)。

## <a name="what-configurations-and-versions-are-available"></a>提供了哪些可用的配置和版本？
在 Azure Marketplace 中，可以看到最新主要版本的映像：Visual Studio 2017 和 Visual Studio 2015。  对于每个主要版本，可以看到最初发布的（也称为 “RTW”）版本，以及“最新”的更新版本。  对于其中每个不同版本，可以找到 Visual Studio Enterprise 和 Visual Studio Community 版本。  我们至少每月更新一次这些映像，以包含最新的 Visual Studio 和 Windows 更新。  映像的名称保持不变，但每个映像的说明将包含已安装的产品版本和映像的截至日期。

|               发行版本              |        版本       |     产品版本     |
|:------------------------------------------:|:---------------------:|:-----------------------:|
| Visual Studio 2017 - 最新（版本 15.5） | Enterprise，Community |      版本 15.5.3     |
|         Visual Studio 2017 - RTW           | Enterprise，Community |      版本 15.0.7     |
|   Visual Studio 2015 - 最新（更新 3）   | Enterprise，Community |  版本 14.0.25431.01  |
|         Visual Studio 2015 - RTW           |         无          | （已过维护期限） |

> [!NOTE]
> 根据 Microsoft 服务策略，最初发布的（也称为“RTW”）Visual Studio 2015 版本已过维护期限。  因此，Visual Studio 2015 Update 3 是 Visual Studio 2015 产品系列仅剩的版本。

有关详细信息，请参阅 [Visual Studio 服务策略](https://www.visualstudio.com/en-us/productinfo/vs-servicing-vs)。

## <a name="what-features-are-installed"></a>安装了哪些功能？
每个映像都包含针对该 Visual Studio 版本的建议功能集。  通常情况下，安装包括：

* 所有可用的工作负载，包括该工作负载的建议可选组件
* .NET 4.6.2 和 .NET 4.7 SDK、目标包和开发人员工具
* Visual F#
* 适用于 Visual Studio 的 GitHub 扩展
* LINQ to SQL 工具

这是我们在生成映像时用于安装 Visual Studio 的命令行：

```
    vs_enterprise.exe --allWorkloads --includeRecommended --passive ^
       add Microsoft.Net.Component.4.7.SDK ^
       add Microsoft.Net.Component.4.7.TargetingPack ^ 
       add Microsoft.Net.Component.4.6.2.SDK ^
       add Microsoft.Net.Component.4.6.2.TargetingPack ^
       add Microsoft.Net.ComponentGroup.4.7.DeveloperTools ^
       add Microsoft.VisualStudio.Component.FSharp ^
       add Component.GitHub.VisualStudio ^
       add Microsoft.VisualStudio.Component.LinqToSql
```

如果映像不包含你需要的 Visual Studio 功能，请通过反馈工具（页面右上角）提供反馈。

## <a name="what-size-vm-should-i-choose"></a>我应该选择哪种大小的 VM？
预配新的虚拟机很简单，Azure 提供了一系列虚拟机大小。  与购置任何硬件一样，你希望高性价比。  因为 Visual Studio 是一个功能强大的多线程应用程序，所以你需要至少包含 2 个处理器和 7 GB 内存的 VM 大小。 在 Azure 中，它转换为至少需要以下这些 VM 大小：

   * Standard_D2_v3
   * Standard_D2s_v3
   * Standard_D4_v3
   * Standard_D4s_v3
   * Standard_D2_v2
   * Standard_D2S_v2
   * Standard_D3_v2

有关最新虚拟机大小的详细信息，请参阅 [Azure 中的 Windows 虚拟机大小](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sizes)。

在 Azure 中，你不必拘泥于第一次的选择，你可以通过调整 VM 的大小重新平衡最初的选择。  可以预配大小更为合适的新 VM，也可以根据不同的基础硬件调整现有 VM 的大小。  有关详细信息，请参阅[调整 Windows VM 大小](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/resize-vm)。

## <a name="after-i-get-the-vm-running-then-what"></a>VM 开始运行后我该做什么？
Visual Studio 在 Azure 中遵循“自带许可”模型。  因此，与在专有硬件上的安装类似，第一步都包括许可 Visual Studio 安装。  你可以通过使用与 Visual Studio 订阅关联的 Microsoft 帐户登录来解锁 Visual Studio，也可以通过使用最初购买时提供的产品密钥来解锁 Visual Studio。  有关详细信息，请参阅[登录到 Visual Studio](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) 和[如何解锁 Visual Studio](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-unlock-visual-studio)。

## <a name="after-i-build-out-the-dev-vm-how-do-i-save-capture-it-for-future-or-team-use"></a>构建开发人员 VM 后，如何保存（捕获）它以供以后或团队使用？

开发环境的范围非常大，构建更为复杂的环境将产生高昂的成本。  但是，无论你的环境如何配置，Azure 都可以通过将你完美配置的 VM 保存/捕获为“基本映像”以供你自己和/或团队其他成员日后使用，轻松节省这项投资。  然后，在启动新的 VM 时，从基本映像而不是从 Marketplace 映像对其进行预配。

简而言之，你将需要 Sysprep 并关闭正在运行的 VM，然后通过 Azure 门户的 UI 来捕获（图 1） VM 作为映像。  Azure 将在你所选的存储帐户中保存包含映像的 `.vhd` 文件。  然后，新映像将在你的资源订阅列表中显示为映像资源。

<img src="media/capture-vm.png" alt="Capture an image through the Azure portal’s UI" style="border:3px solid Silver; display: block; margin: auto;"><center>*（图 1）通过 Azure 门户 UI 捕获映像*</center>

有关详细信息，请参阅[将 VM 捕获到映像](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/capture-image-resource)。

  提醒：不要忘记 sysprep VM！  如果遗漏该步骤，则 Azure 无法从映像预配 VM。

> [!NOTE]
> 存储映像仍会产生一定的费用，但与从头开始为需要 VM 的团队成员重新构建 VM 所产生的人力成本相比，增加的这点成本就无关紧要了。  例如，每月创建和存储 127 GB 的映像供团队所有成员重复使用需要几美元。  但是，与每个员工投入数小时构建和验证正确配置的开发框供其个人使用相比，这些成本微不足道。

此外，你的开发任务或技术可能需要更大的规模，例如各种开发配置和多个计算机配置。  可以使用 Azure DevTest 实验室来创建可自动构建你的“黄金映像”的菜谱，并管理有关团队运行 VM 的策略。  [使用适用于开发人员的 Azure DevTest 实验室](https://docs.microsoft.com/en-us/azure/devtest-lab/devtest-lab-developer-lab)是详细了解 Azure DevTest 实验室的最佳来源。

## <a name="next-steps"></a>后续步骤
现在你知道有关预配置的 Visual Studio 映像的信息，下一步是创建新 VM：

* [通过 Azure 门户创建 VM](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal)
* [Windows 虚拟机概述](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/overview)
