---
title: 创建 Visual Studio 脱机安装缓存
description: 了解如何脱机安装 Visual Studio。
ms.custom: ''
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d19eabe10234ca2a1670ae04f99a45a85a6cac14
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "43138872"
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>创建 Visual Studio 2017 脱机安装缓存

我们精心设计的 Visual Studio 2017 安装程序可以在各种网络和计算机条件下完成安装。

- 我们采用了基于工作负载的新模型。这意味着需要下载的内容比旧版 Visual Studio 要少得多：最小安装只需 300 MB；
- 我们不会下载通用的“ISO”或 zip 文件，而是仅下载你的计算机所需的程序包。 例如，如果你不需要 64 位文件，我们就不下载；
- 在安装过程中，我们会尝试三种不同的下载技术（WebClient、BITS 和 WinInet），以最大限度地减少对防病毒和代理软件的干扰；
- 安装 Visual Studio 所需的文件已发布到覆盖全球的传送网络上，因此我们可以从本地服务器为你获取这些文件。

我们建议你尝试 [Visual Studio Web 安装程序](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) &mdash; 你会获得良好的体验。

 > [!div class="button"]
 > [下载 Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

如果因为 Internet 连接不可用或不可靠而希望进行脱机安装，请参阅[在低带宽或不可靠的网络环境中安装 Visual Studio 2017](../install/install-vs-inconsistent-quality-network.md)。 可以使用命令行为脱机安装所需的文件创建本地缓存。 此过程会替换用于安装以前版本的 ISO 文件。

> [!NOTE]
> 如果你是企业管理员，并且要将 Visual Studio 2017 部署到客户端工作站网络（与 Internet 之间设有防火墙），请参阅[创建 Visual Studio 2017 的网络安装](../install/create-a-network-installation-of-visual-studio.md)和[安装 Visual Studio 脱机安装所需的证书](../install/install-certificates-for-visual-studio-offline.md)页。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]
