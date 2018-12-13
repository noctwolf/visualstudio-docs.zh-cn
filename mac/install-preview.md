---
title: 安装预览版
description: 更新 Visual Studio for Mac 和访问预览版（包括 Visual Studio 2019 for Mac 预览版）的相关说明。
zone_pivot_groups: mac-ide-version
author: conceptdev
ms.author: crdun
ms.date: 11/03/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 0E1EF257-9DE4-4653-9DF4-805CE007A1A1
ms.openlocfilehash: b5eea8c2c894b7eeaa13c83ae6698d1297de9297
ms.sourcegitcommit: ae46be4a2b2b63da7e7049e9ed67cd80897c8102
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2018
ms.locfileid: "52896752"
---
# <a name="install-a-preview-release"></a>安装预览版

::: zone pivot="vsmac2019"

> [!TIP]
> Visual Studio 2019 for Mac 预览版现已发布。 这是预览版第一次与 Visual Studio for Mac 的最新稳定版本并行安装。

## <a name="requirements-for-the-visual-studio-2019-for-mac-preview"></a>Visual Studio 2019 for Mac 预览版要求

* 配备 macOS High Sierra 10.13 或更高版本的 Mac。

要为 iOS 或 macOS 构建 Xamarin 应用，还需要：

* Xcode 10.0 或更高版本。 通常建议使用稳定的最新版本。
* 一个 Apple ID。 如果没有 Apple ID，请在 https://appleid.apple.com 新建一个。 需要 Apple ID 才可安装和登录 Xcode。

## <a name="installing-the-preview"></a>安装预览版

1. 从 [Visual Studio for Mac 预览页](https://aka.ms/vs4mac-preview)下载预览版安装程序。
2. 下载完成后，单击 VisualStudioforMacPreviewInstaller.dmg 以装载安装程序，然后通过双击箭头徽标运行它：

    [![单击大箭头开始安装](media/install-preview-installer-sml.png)](media/install-preview-installer.png#lightbox)

3. 可能会收到有关从 Internet 下载应用程序的警告。 单击“打开”。
4. 安装程序检查系统时，请耐心等待：

    [![安装程序会检查系统中是否有已安装的组件](media/install-preview-checking-sml.png)](media/install-preview-checking.png#lightbox)

5. 将出现一条警告，要求确认隐私和许可条款。 请点击链接仔细阅读，如果同意，则按“继续”：

    [![请点击隐私和条款的链接，如果同意，请继续](media/install-preview-privacy-sml.png)](media/install-preview-privacy.png#lightbox)

6. 此时显示可用的工作负载列表。 选择你要使用的工作负载：

    [![选择要安装的可选工作负载功能](media/install-preview-selection-sml.png)](media/install-preview-selection.png#lightbox)

    如果当前的 Visual Studio for Mac 2017 版本低于 7.7 版，系统会要求你同意升级到最新的稳定版本（这是支持并行安装所必需的）。 按“继续”同意升级：

    ![需要将稳定版本升级到 7.7](media/install-preview-older-upgrade.png)

7. 完成选择后，按下“安装”按钮。
8. 安装程序将在下载并安装 Visual Studio for Mac 和所选工作负载时显示进度。 系统可能会提示输入密码以授予安装所需的权限。
9. 可以随时使用 Visual Studio（预览版）测试预览版本，或者切换回最新的稳定版 Visual Studio 以进行生产工作。 两个图标如下所示：

    ![稳定版和预览版的图标差异](media/install-preview-icons-sml.png)

如果在企业环境中安装时遇到网络问题，请查看[在有防火墙或代理的情况下进行安装](https://docs.microsoft.com/visualstudio/mac/installation#install-visual-studio-for-mac-behind-a-firewall-or-proxy-server)的说明。

了解有关[发行说明](https://docs.microsoft.com/visualstudio/releasenotes/vs2019-mac-preview-relnotes)中的更改详细信息。

::: zone-end
::: zone pivot="vsmac2017"

## <a name="install-an-update-for-visual-studio-2017-for-mac"></a>安装 Visual Studio 2017 for Mac 的更新

新版 Visual Studio for Mac 在正式发布前是作为预览版提供。 在新功能和最新 bug 修补程序完全纳入产品之前，用户可通过预览版抢先尝试这些功能并获取最新修补程序。

Visual Studio for Mac 的预览版是作为更新发布的，而不是通过单独下载发布。 如[更新](update.md)一文所述，Visual Studio for Mac 具有三个更新通道：稳定版本、Beta 版本和 Alpha 版本。

大多数预览版都可通过 Beta 版本和 Alpha 版本通道获取，但请务必查看[预览版发布说明](/visualstudio/releasenotes/vs2017-mac-preview-relnotes)，了解最准确的信息。

若要安装 Visual Studio for Mac 预览版，请执行以下步骤：

1. 转到“Visual Studio”>“检查更新”。
2. 在更新通道组合框中，选择“Beta 版本”。
3. 选择“切换通道”按钮，切换到所选通道并开始下载任何新更新。
4. 选择“重启并安装更新”按钮，开始安装更新。

有关在 Visual Studio for Mac 中更新的详细信息，请参阅[更新](update.md)一文。

::: zone-end