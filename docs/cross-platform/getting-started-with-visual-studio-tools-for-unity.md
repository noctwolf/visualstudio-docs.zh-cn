---
title: Visual Studio Tools for Unity 入门 | Microsoft Docs
ms.custom: ''
ms.date: 07/03/2018
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 66b5b4eb-13b5-4071-98d2-87fafa4598a8
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: dbe546f43b0a66abc78b94480894b63dc4f5eafa
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283102"
---
# <a name="get-started-with-visual-studio-tools-for-unity"></a>Visual Studio Tools for Unity 入门

## <a name="install-visual-studio"></a>安装 Visual Studio

### <a name="unity-bundled-installation"></a>Unity 捆绑安装

自 Unity 2018.1 起，Visual Studio 为 Unity 的默认 C# 脚本编辑器，并且包含在 Unity 下载助手和 Unity 中心安装工具中。

- 前往 [store.unity.com](https://store.unity.com/) 下载 Unity。

安装期间，请确保 Visual Studio 签入组件列表以使用 Unity 进行安装：

#### <a name="unity-hub"></a>Unity 中心

![unity 中心安装](media/vstu_unity-hub.png)

#### <a name="unity-download-assistant"></a>Unity 下载助手

![unity 下载助手安装](media/vstu_download-assistant.png)

#### <a name="check-for-updates-to-visual-studio"></a>检查 Visual Studio 的更新

随附于 Unity 安装的 Visual Studio 版本可能不是最新版本。 建议检查更新，确保可访问最新工具和功能。

- [更新 Visual Studio](../install/update-visual-studio.md)

### <a name="manual-installation"></a>手动安装

如果已安装 Visual Studio 2017 或者希望手动安装，请运行“Visual Studio 安装程序”。

1. [下载 Visual Studio 安装程序](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio)，如已安装，则打开它。

1. 为所需的 Visual Studio 版本单击“修改”（如已安装）或“安装”（适用于新安装）。

1. 在“工作负载”选项卡上，滚动到“移动和游戏”部分，并选择“使用 Unity 的游戏开发”工作负载。

    ![Unity 工作负载](media/vstu_unity-workload.png)

1. 单击安装程序窗口右下角的“修改”（如已安装）或“安装”（适用于新安装）。

## <a name="configure-unity-for-use-with-visual-studio"></a>配置用于 Visual Studio 的 Unity

自 Unity 2018.1 起，Visual Studio 应为 Unity 的默认外部脚本编辑器。 可以确认下是否如此，或者将外部脚本编辑器更改为特定版本的 Visual Studio：

1. 从“编辑”菜单选择“首选项”。

  ![选择首选项](media/vstu_unity-preferences.png)

1. 在“首选项”对话框中，选择“外部工具”选项卡。

1. 从“外部脚本编辑器”下拉列表中，选择所需版本的 Visual Studio（如果列出此项），否则选择“浏览...”。

  ![选择 Visual Studio](media/vstu_unity-external-tools.png)

1. 如果已选择“浏览...”，导航到 Visual Studio 安装目录中的“Common7/IDE”目录，然后选择“devenv.exe”。 然后单击“打开”。

  ![选择“打开”](media/vstu_browse-for-application.png)

1. 在“外部脚本编辑器”列表中选择 Visual Studio 后，确认已选中“编辑器连接”复选框。

1. 关闭“首选项”对话框以完成配置过程。

## <a name="support-for-older-versions"></a>支持旧版本

 从 Visual Studio Marketplace 下载并安装 Visual Studio Tools for Unity。 你需要安装所用 Visual Studio 版本的正确软件包。

- 对于 Visual Studio 2015 Community、Visual Studio 2015 Professional 或 Visual Studio 2015 Enterprise：

   [下载 Visual Studio 2015 Tools for Unity](https://marketplace.visualstudio.com/items?itemName=SebastienLebreton.VisualStudio2015ToolsforUnity)

> [!NOTE]
> Visual Studio Tools for Unity 要求 Unity 5.2 和更高版本，以及支持扩展的 Visual Studio 版本，例如，Visual Studio Community、Professional、Premium 或 Enterprise。 若要验证你安装的 Unity 是否启用了 Visual Studio Tools for Unity，请从“帮助”菜单中选择“关于 Unity”，并在对话框左下角查看“Microsoft Visual Studio Tools for Unity 已启用”文本。
> ![关于 Unity](media/vstu_about-unity.png)

## <a name="next-steps"></a>后续步骤

 要学习如何在 Visual Studio 中使用和调试 Unity 项目，请参阅 [Visual Studio Tools for Unity](../cross-platform/using-visual-studio-tools-for-unity.md)。
