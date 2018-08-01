---
title: 验证 Xamarin 环境 | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: fd39882e-06d1-4b39-80d2-4d07b6e4f8f5
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 83dfac08058e8b01b6c6d007461f3468e91b396c
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233082"
---
# <a name="verify-your-xamarin-environment"></a>验证 Xamarin 环境

安装程序完成安装后（请参阅） [Setup and install](../cross-platform/setup-and-install.md)，请花几分钟时间验证体验 Xamarin 开发所需的一切就绪。

 安装验证完成后，可尝试执行以下一个或两个演练：

-   [学习在 Visual Studio 中使用 Xamarin.Forms 生成应用的基础知识](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md)，然后构建一个 Xamarin.Forms 应用。

-   [在 Visual Studio 中使用 Xamarin 生成具有本机 UI 的应用](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md)，在每个平台上都使用本机用户界面，但共享 .NET Standard 库中的部分代码。

## <a name="all-platforms"></a>所有平台

在 Visual Studio 中，首先选择“工具” > “扩展和更新”，然后检查是否有任何 Xamarin 组件需要更新。

然后，使用“文件” > “新建项目”在 Visual Studio 中创建一个新的 Xamarin.Forms 解决方案。 在对话框中，展开“Visual C#” > “跨平台”，选择“移动应用 (Xamarin.Forms)”，然后单击“确定”。 在下一个对话框中，选择“空白应用”。 在“代码共享策略”下，选择“.NET Standard”。 单击 **“确定”**。

上述操作创建的解决方案包含四个项目：一个共享 .NET Standard 2.0 库项目、一个适用于 Android 的应用程序项目，一个适用于 iOS 的应用程序项目以及一个通用 Windows 平台 (UWP)：

![利用空白应用“Xamarin.Forms”模板新建项目的结果](../cross-platform/media/crossplat-xamarin-verify-1.png "CrossPlat Xamarin Verify 1")

## <a name="android"></a>Android

1. 转到“工具”>“Android”>“Android SDK 管理器”，检查是否已安装最新的 Android SDK 工具。 安装最新版本的 Android SDK 工具、Android SDK 平台工具和 Android SDK 生成工具。 无需始终安装最新的 Android API 级别。 所需的 API 级别取决于要面向的平台级别。 通常，安装 Xamarin 平台时会随附安装其所需的 Android 平台级别。

2.  在设备或模拟器上验证生成和调试：

    -   右击“解决方案资源管理器”中的 Android 项目，并选择“设为启动项目” 。

    -   工具栏中应显示一个下拉列表，其中包含一系列可用的 Android 设备和模拟器。

    必须在 Android 设备的“设置”页的“开发人员”选项中启用设备的 USB 调试。 然后使用 USB 线将该设备连接到计算机。

    此处还会列出模拟器。 从中选择一个设备或 Visual Studio 模拟器：

  ![选择适用于 Android 的 Visual Studio 模拟器作为调试目标](../cross-platform/media/crossplat-xamarin-verify-3.png "CrossPlat Xamarin Verify 3")

  有关详细信息，请参阅 Visual Studio ALM 博客 [Introducing Visual Studio's Emulator for Android](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx)（适用于 Android 的 Visual Studio 模拟器简介）。 如果使用模拟器时遇到问题，请参阅[适用于 Android 的 Visual Studio 模拟器疑难解答](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md)。 还可选择“工具”>“Android”>“Android Emulator 管理器 ”，为模拟器创建新的设备配置文件。

3. 按 F5 编译程序并将其部署到 Android 设备或模拟器。

## <a name="windows"></a>Windows

1.  右键单击解决方案资源管理器中的通用 Windows 项目，选择“设为启动项目”。

2.  在“解决方案平台”下拉列表中，选择“x86”或“x64”。 选择“本地计算机”。

3.  按 F5 将程序部署到桌面。

## <a name="ios"></a>iOS

1.  确保 Mac 已联网且已与 Visual Studio 配对，如 [连接到 Mac](/xamarin/ios/get-started/installation/windows/connecting-to-mac/) 中所述。

2.  右击“解决方案资源管理器”中的 iOS 项目，并选择“设为启动项目” 。

3.  如下所示，从 Visual Studio 的生成下拉菜单中选择“iPhoneSimulator”目标；或者，如果设备限于 Mac，请选择“iPhone”目标。

 ![选择 iPhoneSimulator 生成目标](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin Verify 5")

 如果未列出任何模拟器，请在 Mac 上启动 Xcode，选择“Xcode” > “首选项”，然后单击“下载”。 在“组件”标题下，应显示可供下载的模拟器版本。 在 [iOS 调试](/xamarin/ios/deploy-test/debugging-in-xamarin-ios)页上可以找到关于调试的其他说明。

4.  从 Visual Studio 下拉列表中选择模拟器设备目标：

 ![选择 iPhone 调试目标](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin Verify 6")

5. 按 F5 启动调试器。 模拟器在 Mac 上启动，此时你可以与应用进行交互，同时在 Visual Studio 中进行调试。 如果 iPhone 或 iPad 实物已连接到 Mac，列表中将出现该设备，你可以选择该设备。 如果未列出任何设备或模拟器，请检查与 Mac 的连接情况。 请参阅上文步骤 1 中链接指向的文章，或转到“工具” > “iOS” > “与 Mac 配对”

6.  如果在连接到 Mac 时遇到问题，请参阅[连接疑难解答](/xamarin/ios/get-started/installation/windows/connecting-to-mac/troubleshooting/)。

7.  如果看到错误显示“安装的配置文件与安装的 iOS 签名密钥不匹配”，请尝试以下建议：

  - 检查是否按[将帐户添加到 Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com) 中所述在 Mac 上的 Xcode 中添加了 Apple ID 帐户。  添加帐户后，请重启 Visual Studio 和 Xcode。

  - 在 iOS 捆绑签名选项卡的 iOS 项目属性中，验证活动调试配置的“自定义”授权字段是否为空。  注意：如果遇到以上错误消息，则应仅尝试删除此设置。

  ![CrossPlat Xamarin 验证 8](../cross-platform/media/crossplat-xamarin-verify-8.png "CrossPlat Xamarin 验证 8")
