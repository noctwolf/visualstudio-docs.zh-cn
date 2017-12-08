---
title: "安装 Visual Studio for Mac | Microsoft Docs"
description: "有关如何安装 Visual Studio for Mac 和跨平台开发所需附加组件的说明。"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.openlocfilehash: 25d3227bcf8a18a2fc6ba68c194e9cac75b2e919
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="setup-and-install-visual-studio-for-mac"></a>设置和安装 Visual Studio for Mac

## <a name="setup"></a>安装

下载 Visual Studio for Mac 后，要开始开发本机跨平台应用，还需先安装并设置一些其他内容。

要结合使用 iOS 和 Visual Studio，需要以下各项：

* 运行 macOS Sierra 10.12 或更高版本的 Mac
* Xcode 8.3
* 一个 Apple ID。 如果没有 Apple ID，请在 https://appleid.apple.com 新建一个。需要 Apple ID 才可安装和登录 Xcode。

## <a name="install"></a>安装

1. 从 [https://www.visualstudio.com/](https://www.visualstudio.com/) 下载 Visual Studio for Mac

2. 下载安装包后，单击“VisualStudioInstaller.dmg”文件装载安装程序，然后通过双击徽标运行它，如下图所示：

  ![安装程序对话框](media/installer-image1.png)

3. 系统可能会通过警报对话框发出提示，如下图所示。 在此情况下，请单击“打开”：

  ![警报对话框](media/installer-image2.png)

4. 安装程序会检查系统，确定需要安装或更新的组件：

  ![评估系统](media/installer-image3.png)

5. 之后，会出现一个警报对话框，要求确认隐私和许可条款。 按“继续”按钮接受条款：

  ![许可对话框](media/installer-image4.png)

6. 安装程序会列出缺少和需要下载并安装的所需组件。 在此处选择要下载的产品：

  ![选择项](media/installer-image5.png)

  此安装屏幕显示每个组件的版本和大小。 可单击每个组件查看该组件的依赖项列表（对于 Android），该组件下载的其他包（对于 .NET Core），或任何其他所需应用程序（对于 iOS 和 macOS）：

  ![Android 附加依赖项](media/installer-image6.png)

7. 确认选择后，选择“安装和更新”按钮开始安装过程。

8. 安装程序会启动所选项的下载和安装过程：

  ![开始安装](media/installer-image7.png)

  ![下载 Xamarin.Mac](media/installer-image8.png)

  ![完成安装](media/installer-image9.png)

9. 系统可能会提示为完成安装所需的各个组件提升必要的权限。 在此处输入管理员凭据以继续安装过程：

  ![输入权限以继续执行安装程序](media/installer-image10.png)

10. 安装成功后，可通过按“开始”，开始在 Visual Studio 中开发应用：

  ![打开 Visual Studio](media/installer-image11.png)

> [!NOTE]
如果在原始安装期间选择不安装平台或工具（通过在步骤 #6 中取消选择相关选项），且希望稍后添加该组件，必须再次运行[安装程序](https://www.visualstudio.com/vs/)。

## <a name="manual-installation"></a>手动安装

如果安装失败或任何单个组件的安装失败，可能能够通过手动安装解决问题。 若要查看所需的组件并逐个下载，请执行以下步骤：

1. 在 Visual Studio 安装程序的第二个屏幕上，转到菜单栏并选择“查看手动安装说明”：

    ![显示手动安装菜单项的选项](media/installer-image12.png)

2. 按照说明下载并手动安装组件：

  ![“手动安装”对话框](media/installer-image13.png)

## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>在防火墙或代理服务器后安装 Visual Studio for Mac

若要在防火墙后面安装 Visual Studio for Mac，必须将某些终结点设置为可供访问，以允许下载所需的工具和更新软件。

配置网络以允许访问下列位置：

* [Visual Studio 终结点](https://docs.microsoft.com/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)