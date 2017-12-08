---
title: "禁用或移动包缓存 | Microsoft Docs"
description: "禁用、启用或移动部署 Visual Studio 时使用的包缓存。"
ms.date: 04/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cache
- nocache
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 2429993A-3F0E-41C5-9562-FEA6AE994440
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: f279a97cc91aa2ed3fa2efe5df21aaa90ddc5271
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2017
---
# <a name="disable-or-move-the-package-cache"></a>禁用或移动包缓存

如果需要在未连接 Internet 的情况下修复 Visual Studio 或其他相关产品，可以使用包缓存提供的已安装的包源。 不过，在安装一些驱动器或系统后，可能不希望保留所有这些包。
由于安装程序会在需要时下载它们，因此如果希望节省或恢复磁盘空间，可以禁用或移动包缓存。

## <a name="disable-the-package-cache"></a>禁用包缓存

使用新安装程序安装、修改或修复 Visual Studio 或其他产品之前，可以使用 `--nocache` 开关来启动安装程序。

```
"%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\vs_installer.exe" --nocache
```

对任意产品执行任何操作都会删除相应产品的任何现有包，并避免在安装后保存任何包。 如果修改或修复 Visual Studio 且必须使用包，那么它们会自动进行下载，并在安装后进行删除。

若要重新启用缓存，请改为传递 `--cache`。 由于只会缓存必需的包，因此，如果需要还原所有包，应在断开网络连接之前修复 Visual Studio。

```
"%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\vs_installer.exe" repair --passive --norestart --cache
```

还可以在安装、修改或修复 Visual Studio 之前设置 `KeepDownloadedPayloads` [注册表策略](set-defaults-for-enterprise-deployments.md)来禁用缓存。

## <a name="move-the-package-cache"></a>移动包缓存

常见的系统配置是将 Windows 安装在硬盘较大（或更大）且可满足开发需求（如源代码、程序二进制文件等）的 SSD 上。 如果要脱机工作，可以改为移动包缓存。

目前，只有在安装、修改或修复 Visual Studio 之前设置了 `CachePath` [注册表策略](set-defaults-for-enterprise-deployments.md)后，才能执行此操作。

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户）。

## <a name="see-also"></a>请参阅

 * [安装 Visual Studio](install-visual-studio.md)
 * [为企业部署设置默认值](set-defaults-for-enterprise-deployments.md)
 * [使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
