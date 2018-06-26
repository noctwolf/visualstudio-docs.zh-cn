---
title: 设置 Visual Studio for Mac Tools for Unity
description: 设置和安装用于 Visual Studio for Mac 的 Unity 工具
author: dantogno
ms.author: v-davian
ms.date: 05/25/2018
ms.assetid: 83FDD7A3-5D16-4B4B-9080-078E3FB5C623
ms.openlocfilehash: 18839ce37feb4f2a113c4a8875ce1c25ddba31e1
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573266"
---
# <a name="setup-visual-studio-for-mac-tools-for-unity"></a>设置 Visual Studio for Mac Tools for Unity

本部分介绍如何开始使用 Visual Studio for Mac Tools for Unity。

## <a name="install-visual-studio-for-mac"></a>安装 Visual Studio for Mac

### <a name="unity-bundled-installation"></a>Unity 捆绑安装

自 Unity 2018.1 起，Visual Studio for Mac 为 Unity 的默认 C# IDE，并且包含在 Unity 下载助手和 Unity 中心安装工具中。 前往 [store.unity.com](https://store.unity.com/) 下载 Unity。

安装期间，请确保 Visual Studio for Mac 签入组件列表以使用 Unity 进行安装：

#### <a name="unity-hub"></a>Unity 中心

![unity 中心安装](media/setup-vsmac-tools-unity-image7.png)

#### <a name="unity-download-assistant"></a>Unity 下载助手

![unity 下载助手安装](media/setup-vsmac-tools-unity-image8.png)

#### <a name="check-for-updates-to-visual-studio-for-mac"></a>检查 Visual Studio for Mac 的更新

随附于 Unity 安装的 Visual Studio for Mac 版本可能不是最新版本。 建议检查更新，确保可访问最新工具和功能。

* [更新 Visual Studio for Mac](update.md)

### <a name="manual-installation"></a>手动安装

如果已有 Unity 5.6.1 或更高版本，但没有 Visual Studio for Mac，可以手动安装 Visual Studio for Mac。 Visual Studio for Mac 的所有版本绑定 Visual Studio for Mac Tools for Unity，包括免费的 Community Edition：

* 前往 [visualstudio.com](https://www.visualstudio.com/) 下载 Visual Studio for Mac。
* Visual Studio for Mac Tools for Unity 将在安装过程中自动安装。
* 请按照[安装指南](installation.md)中的步骤获取其他安装帮助。

> [!NOTE]
> Visual Studio for Mac Tools for Unity 工具需要 5.6.1 或更高 Unity 版本。 若要验证你的 Unity 版本是否启用了 Visual Studio for Mac Tools for Unity，请从 Unity 菜单中选择“关于 Unity”，并在对话框左下角查看“Microsoft Visual Studio Tools for Unity 已启用”文本。
>
> ![关于 Unity](media/setup-vsmac-tools-unity-image3.png)

## <a name="confirm-that-the-visual-studio-for-mac-tools-for-unity-extension-is-enabled"></a>确认启用 Visual Studio for Mac Tools for Unity 扩展

虽然应默认启动 Visual Studio for Mac Tools for Unity 扩展，但也可以检查安装版本号确认这一点：

1. 在 Visual Studio 菜单中，选择“扩展...”。

  ![选择扩展](media/setup-vsmac-tools-unity-image1.png)

1. 展开“游戏开发”部分，确认 Visual Studio for Mac Tools for Unity。

  ![查看 Unity 条目](media/setup-vsmac-tools-unity-image2.png)

## <a name="configure-unity-for-use-with-visual-studio-for-mac"></a>配置用于 Visual Studio for Mac 的 Unity

自 Unity 2018.1 起，Visual Studio 应为 Unity 的默认外部脚本编辑器。 可以确认下是否如此，或者将外部脚本编辑器更改为 Visual Studio：

1. 从 Unity 菜单选择“首选项...”。

  ![选择首选项](media/setup-vsmac-tools-unity-image4.png)

1. 在“首选项”对话框中，选择“外部工具”选项卡。

1. 从“外部脚本编辑器”下拉列表中，选择“Visual Studio”（如果列出此项），否则选择“浏览...”。

  ![选择 Visual Studio](media/setup-vsmac-tools-unity-image5.png)

1. 如果已选择“浏览...”，导航到“应用程序目录”，选择“Visual Studio”，然后单击“打开”。

  ![选择“打开”](media/setup-vsmac-tools-unity-image6.png)

1. 在“外部脚本编辑器”列表中选择 Visual Studio 之后，关闭首选项对话框完成配置流程。
