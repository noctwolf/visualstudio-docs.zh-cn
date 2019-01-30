---
title: 安装 Dotfuscator Community Edition (CE)
ms.date: 06/22/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.topic: conceptual
keywords: Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, 保护, 社区版, 混淆, .NET, 免费, Visual Studio 2017, 安装
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator installer
- Dotfuscator setup
- install Dotfuscator
- installing Dotfuscator
- set up Dotfuscator
description: 了解如何安装 Visual Studio 2017 中包含的免费 Dotfuscator Community Edition。
ms.assetid: f2146651-e24a-4e24-ade8-8ddee8ff4e43
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1ce5d7204eaa93fe63fc9ffa49e7ef422d028e76
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54988163"
---
# <a name="install-dotfuscator-community-edition-ce"></a>安装 Dotfuscator Community Edition (CE)

Visual Studio 2017 引入了一种影响较小的新式安装体验。
因此，默认情况下不安装 Dotfuscator Community Edition (Dotfuscator CE)。
但是，即使已安装了 Visual Studio，仍可轻松安装 Dotfuscator CE。

> [!NOTE]
> 除了 Visual Studio 版本附带的 Dotfuscator CE 版本外，PreEmptive Solutions 还定期在其网站上提供更新的版本。
> 如果想要直接下载**最新版本**而非从 Visual Studio 中安装，请**[单击此处转到 Dotfuscator 下载页面][download]**。

## <a name="within-visual-studio"></a>在 Visual Studio 中

可从 Visual Studio IDE 中安装 Dotfuscator CE：

1. 在“快速启动”(Ctrl+Q) 搜索栏中，键入 `dotfuscator`。 <br/> <br/> ![快速启动](media/install_from_vs_12.png) <br/> <br/>
2. 在显示的快速启动结果中的“安装”标题下，选择“PreEmptive Protection - Dotfuscator (各个组件)”。
   * 如果“菜单”标题下显示的是“工具”-“PreEmptive Protection - Dotfuscator”，则表示已经安装了 Dotfuscator CE。 有关使用方法的详细信息，请参阅[完整 Dotfuscator CE 用户指南的入门页][get-started]。
3. “Visual Studio 安装程序”窗口将会启动，并为安装 Dotfuscator CE 进行预配置。
   * 可能需要提供管理员凭据才能继续。
4. 关闭 Visual Studio IDE 的所有实例。 <br/> <br/> ![单击“安装”](media/install_from_vs_345.png) <br/> <br/>
5. 在 Visual Studio 安装程序窗口中，单击“安装”。

安装完成后即可开始使用 Dotfuscator CE。 有关详细信息，请参阅[完整 Dotfuscator CE 用户指南的入门页][get-started]。

## <a name="during-visual-studio-installation"></a>Visual Studio 安装过程

如果尚未安装 Visual Studio 2017，可从 [Visual Studio 网站][2017-install]获取安装程序。
运行时，它会显示所选 Visual Studio 版本的安装选项。

![安装选项](media/install_ui.png)

然后可将 Dotfuscator CE 作为 Visual Studio 2017 的单个组件进行安装：

1. 选择“各个组件”选项卡。
2. 在“代码工具”下，勾选“PreEmptive Protection - Dotfuscator”项。<br/> <br/> ![单个组件](media/install_individually_12.png) <br/> <br/>
3. “PreEmptive Protection - Dotfuscator”显示在“摘要”面板的“各个组件”部分下。 <br/> <br/> ![摘要窗格](media/install_individually_3.png) <br/> <br/>
4. 根据环境需要进一步配置任何安装设置。
5. 准备好安装 Visual Studio 后，单击“安装”按钮。

安装完成后即可开始使用 Dotfuscator CE。 有关详细信息，请参阅[完整 Dotfuscator CE 用户指南的入门页][get-started]。

## <a name="see-also"></a>请参阅

[This topic in the full Dotfuscator CE User Guide]: https://www.preemptive.com/dotfuscator/ce/docs/help/

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[2017-install]:  https://visualstudio.microsoft.com/downloads/#vs-2017
[get-started]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

[download]:  https://www.preemptive.com/products/dotfuscator/downloads

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_install.html