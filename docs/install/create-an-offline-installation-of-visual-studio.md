---
title: "创建 Visual Studio 的脱机安装 | Microsoft Docs"
description: "了解如何脱机安装 Visual Studio。"
ms.custom: 
ms.date: 08/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6eb68b00e429db1336f851d6e4789ae0b4c8b803
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>创建 Visual Studio 2017 的脱机安装

我们精心设计了 Visual Studio 2017 安装程序，它非常适合在各种网络和计算机条件下安装 Visual Studio。

- 基于工作负载的新模型的推出意味着，需要下载的内容比旧版 Visual Studio 要少得多：最小安装只需 300 MB；
- 与泛型“ISO”或 zip 文件相比，我们仅下载你的计算机所需的程序包。 例如，如果你不需要 64 位文件，我们就不下载；
- 在安装过程中，我们会尝试三种不同的下载技术（WebClient、BITS 和 WinInet），以最大限度地减少对防病毒和代理软件的干扰；
- 由于安装 Visual Studio 所需的文件发布在全球传送网络上，因此我们可以从本地服务器为你获取这些文件。

建议尝试使用 [Visual Studio Web 安装程序](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL) &mdash; 使用体验一定会让你感到满意。

 > [!div class="button"]
 > [下载 Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)
<br/>

如果因为 Internet 连接不可用或不可靠想进行脱机安装，请参阅[在低带宽或不可靠的网络环境中安装 Visual Studio 2017](../install/install-vs-inconsistent-quality-network.md)。 可以使用命令行创建所需文件的本地缓存，以完成脱机安装。 此过程会替换以前版本可用的 ISO 文件。

> [!NOTE]
> 如果你是企业管理员，并且要将 Visual Studio 2017 部署到客户端工作站网络（与 Internet 之间设有防火墙），请参阅我们的[创建 Visual Studio 2017 的网络安装](../install/create-a-network-installation-of-visual-studio.md)和[在脱机环境中安装 Visual Studio 的特殊注意事项](../install/install-visual-studio-in-offline-environment.md)页面。

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户。）
