---
title: "为 Visual Studio 企业部署设置默认值 | Microsoft Docs"
description: "Visual Studio 企业部署的域策略和其他配置操作。"
ms.date: 05/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- gpo
- policy
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9B7B4608-7A3F-4FF4-BDCE-42D9F7CE6DBA
author: heaths
ms.author: heaths
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f269e9c719ee685567161fbf8d5edb05b17ea9cd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="set-defaults-for-enterprise-deployments-of-visual-studio"></a>为 Visual Studio 企业部署设置默认值

可以设置影响 Visual Studio 部署的注册表策略。 这些策略对新安装程序全局适用，并将影响：

- 与其他版本或实例共享的一些包的安装位置
- 包的缓存位置
- 所有包的缓存位置

可以使用[命令行选项](use-command-line-parameters-to-install-visual-studio.md)设置部分策略，并能在计算机上设置注册表值，也可以在整个组织中使用组策略进行分发。

## <a name="registry-keys"></a>注册表项

可以在多个位置上设置企业默认值，从而能够通过组策略进行控制或在注册表中直接控制。 Visual Studio 会依序检查是否已设置任何企业策略；只要按以下顺序发现了策略值，就会忽略剩余的项。

1. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\Setup`
2. `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\Setup`
3. `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\VisualStudio\Setup`（64 位操作系统）

> [!IMPORTANT]
> 如果你未设置 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\Setup` 项，而是设置其他项之一，则应在 64 位操作系统上同时设置其他两个项。 此问题会在未来的产品更新中得到解决。

一些注册表值会在首次使用时自动设置（如果尚未设置的话）。 这种做法可确保后续安装使用相同的值。 这些值存储在第二个注册表项 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\Setup` 中。

可以设置以下注册表值：

| **名称** | **Type** | **默认** | **说明** |
| -------- | -------- | ----------- | --------------- |
| `CachePath` | `REG_SZ` 或 `REG_EXPAND_SZ` | %ProgramData%\Microsoft\VisualStudio\Packages | 用于存储包清单和有效负载（可选）的目录。 有关详细信息，请了解如何[禁用或移动包缓存](disable-or-move-the-package-cache.md)。 |
| `KeepDownloadedPayloads` | `REG_DWORD` | 1 | 即使在安装后，也仍会保留包有效负载。 随时都可以更改值。 禁用此策略会删除你修复或修改的实例的任何已缓存包有效负载。 有关详细信息，请了解如何[禁用或移动包缓存](disable-or-move-the-package-cache.md)。 |
| `SharedInstallationPath` | `REG_SZ` 或 `REG_EXPAND_SZ` | %ProgramFiles(x86)%\Microsoft Visual Studio\Shared | 用于安装跨 Visual Studio 实例版本共享的一些包的目录。 虽然随时都可以更改值，但更改只会影响今后执行的安装。 不得移动旧位置上已安装的任何产品，否则它们可能无法正常运行。 |

> [!IMPORTANT]
> 如果在执行任何安装后更改 `CachePath` 注册表策略，必须将现有包缓存移到新位置上，并确保其受安全保护，以便 `SYSTEM` 和 `Administrators` 拥有完全控制权限，并且 `Everyone` 拥有读取访问权限。
> 如果无法移动现有缓存或无法确保其受安全保护，可能导致今后执行的安装出现问题。

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

 * [安装 Visual Studio](install-visual-studio.md)
 * [禁用或移动包缓存](disable-or-move-the-package-cache.md)
 * [使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
