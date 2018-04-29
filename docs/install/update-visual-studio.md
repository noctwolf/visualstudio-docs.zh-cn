---
title: 更新 Visual Studio 2017
description: 了解如何逐步将 Visual Studio 更新到最新版本。
ms.date: 03/06/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- update Visual Studio
- change visual studio
- changing Visual Studio
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a524fa630fbe9ea8e1cf4474cab2b7180fe582a8
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="update-visual-studio-2017-to-the-most-recent-release"></a>将 Visual Studio 2017 更新到最新版本

建议更新到[最新版本](/visualstudio/releasenotes/vs2017-relnotes)的 Visual Studio 2017，以便始终获得最新功能、修复和改进。

如果希望在我们发布之前试用任何内容，请同时考虑下载下一个版本的[预览版](/visualstudio/releasenotes/vs2017-preview-relnotes)。

> [!IMPORTANT]
> 若要安装、更新或修改 Visual Studio，必须使用具有管理权限的帐户登录。 有关详细信息，请参阅[用户权限与 Visual Studio](../ide/user-permissions-and-visual-studio.md)。

## <a name="update-visual-studio-2017-version-156-or-later"></a>更新 Visual Studio 2017 版本 15.6 或更高版本

已经简化了安装和更新体验，以便更轻松地在 IDE 中直接使用。 下面介绍了如何从版本 15.6 以及更高版本更新到较新版本的 Visual Studio。

### <a name="use-the-notifications-hub"></a>使用“通知”中心

当有更新时，Visual Studio 中会有相应的“通知”标志。

1. 保存所有内容。

2. 选择“通知”标志打开“通知”中心，然后选择要安装的更新。

  ![使用“通知”中心更新 Visual Studio 2017](media/vs-install-notifications-hub-15dot6.png "Visual Studio 2017 中的“通知”中心")

3. 当“更新”对话框打开，请选择“立即更新”。

    ![使用“通知”中心的“更新”对话框更新 Visual Studio 2017](media/vs-update-now-from-notifications-hub.png "Visual Studio“通知”中心的“更新”对话框")

     如果“用户访问控制”对话框打开，选择“是”。 接下来，“请稍候”对话框可能会打开一段时间，然后 Visual Studio 安装程序会打开以启动更新。

     ![15.6 版中的新 Visual Studio 安装程序体验](media/visual-studio-15dot6-installer.png "15.6 版中的新 Visual Studio 安装程序体验")

     更新将继续。 然后，完成时，将重新启动 Visual Studio。

### <a name="use-the-ide"></a>使用 IDE

可以查看更新，然后从 Visual Studio 菜单栏安装更新。

1. 保存所有内容。

2. 选择“帮助” > “查看更新”。

     ![Visual Studio 版本 15.6 中的新“帮助”菜单](media/vs-help-menu-check-for-updates.png "Visual Studio 版本 15.6 中的新“帮助”菜单")

3. 当“更新”对话框打开，请选择“立即更新”。

   更新将启动（如上一节中所述），然后 Visual Studio 会在更新成功完成后重启。

### <a name="use-the-visual-studio-installer"></a>使用 Visual Studio 安装程序

和 Visual Studio 2017 的早期版本一样，可以使用 Visual Studio 安装程序来安装更新。

1. 保存所有内容。

2. 打开安装程序。 Visual Studio 安装程序可能需要更新才能继续。

  > [!NOTE]
  > 在运行 Windows 10 的计算机上，可以在字母“V”下找到“Visual Studio 安装程序”，也可以在字母“M”下找到“Microsoft Visual Studio 安装程序”。

2. 在安装程序中的“产品”页上，确定已安装的 Visual Studio 版本。

3. 若有更新，会看到“更新”按钮。 （可能需要等待几秒钟的时间，安装程序才能确定是否有更新。）

  选择“更新”按钮来安装更新。

     ![使用 Visual Studio 安装程序更新 Visual Studio 2017](media/update-visual-studio.png "使用 Visual Studio 安装程序更新 Visual Studio 2017")

## <a name="update-visual-studio-2017-version-155-or-earlier"></a>更新 Visual Studio 2017 版本 15.5 或更早版本

如果使用的是早期版本，下面将介绍如何应用从 Visual Studio 2017 版本 15.0 到版本 15.5 的更新。

### <a name="update-by-using-the-notifications-hub"></a>使用“通知”中心进行更新

1. 当有更新时，Visual Studio 中会有相应的“通知”标志。

  ![使用“通知”中心更新 Visual Studio 2017](media/notification-flag.png "Visual Studio 中更新的通知标志")

  选择通知标志，打开“通知”中心。

  ![使用“通知”中心更新 Visual Studio 2017](media/notifications-hub.png "Visual Studio 中的“通知”中心")

2. 选择“有‘Visual Studio 更新’”，随即会打开“扩展和更新”对话框。

  ![使用“通知”中心更新 Visual Studio 2017](media/notifications-hub-select.png "Visual Studio 中的“通知”中心")

3. 在“扩展和更新”对话框中，选择“更新”按钮。

  ![使用“通知”中心更新 Visual Studio 2017](media/notifications-extensions-and-updates.png "Visual Studio 中的“扩展和更新”对话框")

#### <a name="more-about-visual-studio-notifications"></a>Visual Studio 通知的详细信息

Visual Studio 自身或安装的任何组件有更新时，以及 Visual Studio 环境中发生某些事件时，Visual Studio 都会通知你。

* 通知标志呈黄色时，表示有 Visual Studio 产品更新可供安装。
* 通知标志呈红色时，表示许可证有问题。
* 通知标志呈黑色时，表示有要查看的可选消息或信息性消息。

选择通知标志，打开“通知”中心，然后选择想要对其执行操作的通知。 或选择忽略或消除通知。

 ![查看通知中心中的可选消息或信息性消息](media/notification-flag-optional.png "Visual Studio 中可选消息或信息性消息的通知标志")

如果选择忽略通知，Visual Studio 将不再显示它。 如果要重置忽略通知的列表，请选择“通知”中心中的“设置”按钮。

   ![在通知中心内选择“设置”按钮以查看“通知”选项](media/vs-notifications-hub-settings-button.png "在通知中心内选择“设置”按钮以查看“通知”选项")

### <a name="update-by-using-the-visual-studio-installer"></a>使用 Visual Studio 安装程序进行更新

1. 打开安装程序。 可能需要先更新安装程序，然后才能继续操作。 如果确是这种情况，系统会提示你更新安装程序。

  > [!NOTE]
  > 在运行 Windows 10 的计算机上，可以在字母“V”下找到“Visual Studio 安装程序”，也可以在字母“M”下找到“Microsoft Visual Studio 安装程序”。

2. 在安装程序中的“产品”页上，确定已安装的 Visual Studio 版本。

3. 若有更新，会看到“更新”按钮。 （可能需要等待几秒钟的时间，安装程序才能确定是否有更新。）

  选择“更新”按钮来安装更新。

     ![使用 Visual Studio 安装程序更新 Visual Studio 2017](media/update-visual-studio.png "使用 Visual Studio 安装程序更新 Visual Studio 2017")

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [安装 Visual Studio 2017](install-visual-studio.md)
* [修改 Visual Studio 2017](modify-visual-studio.md)
* [卸载 Visual Studio 2017](uninstall-visual-studio.md)
* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
