---
title: 删除 Visual Studio 2017 | Microsoft Docs
description: 了解如何逐步从计算机中彻底删除 Visual Studio。
ms.custom: ''
ms.date: 09/12/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- uninstall
- uninstall Visual Studio
- remove
- remove Visual Studio
- cleanup
- cleanup Visual Studio
- clean up
- clean up Visual Studio
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db775eb56a8328e3688e20ce07ce7d045c97c3c7
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "36280014"
---
# <a name="remove-visual-studio"></a>删除 Visual Studio

如果遇到灾难性错误，并且无法修复或卸载 Visual Studio，可以运行 `InstallCleanup.exe` 工具删除安装文件和产品信息。 如果修复或卸载失败，运行此工具将作为最后的解决措施，并且可能从其他 Visual Studio 安装或其他需要修复的产品中卸载功能。

在下面的说明中，可以使用具有以下行为的不同命令行开关运行此工具：

| 开关 | 行为 |
| ------ | -------- |
| `-i`   | 如果没有传递其他开关，则默认为此开关，并且仅删除主安装目录和产品信息。 如果打算在运行 `InstallCleanup.exe` 工具后重新安装相同的版本，则首选此行为。 |
| `-f`   | 如果指定此开关，则会删除在安装目录外安装的主安装目录、产品信息和大部分其他功能，这些功能可能与其他 Visual Studio 安装或其他产品共享。 如果打算删除 Visual Studio 并且后来不重新安装，则首选此行为。 |

1. 关闭 Visual Studio 安装程序。
2. 打开管理员命令提示符。 要打开管理员命令提示符，请执行以下步骤：
   * 单击“开始”菜单
   * 键入“cmd”。
   * 右键单击“命令提示符” ，然后单击“以管理员身份运行” 。
3. 键入 `InstallCleanup.exe` 实用工具的完整路径，并传递所需的任何命令行开关。 默认情况下，此实用工具的路径如下所示：
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

如果在 Visual Studio 安装程序目录下（始终位于 `%ProgramFiles(x86)%\Microsoft Visual Studio`）没有找到 `InstallCleanup.exe`，请按照说明[安装 Visual Studio](install-visual-studio.md)，并在显示工作负载选择屏幕时关闭窗口，再按照前面的步骤执行。

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://visualstudio.microsoft.com/vs/support/#talktous)。

下面是另外几个支持选项：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [安装 Visual Studio 2017](install-visual-studio.md)
* [更新 Visual Studio 2017](update-visual-studio.md)
* [修改 Visual Studio 2017](modify-visual-studio.md)
* [卸载 Visual Studio 2017](uninstall-visual-studio.md)
