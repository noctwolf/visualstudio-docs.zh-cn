---
title: 安装 Xamarin for Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: 2cfcad00-352c-4161-814c-f5ae32d8ada8
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 8ae03dfe4ed2e72015ca1f7d91153d862f44ce40
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="setup-and-install"></a>设置和安装

要在 Xamarin 中利用常见的 C#/.NET 代码基生成本机 iOS、Android 和 Windows 应用，需要具备以下硬件和软件：

-   若要生成 Windows 和 Android 应用：安装了 Visual Studio 2017（包括 Xamarin 开发功能）的 Windows 开发计算机（不是虚拟机）。  

-   若要生成 iOS 应用：安装了 XCode 和 Visual Studio for Mac 且操作系统为 macOS Sierra 10.12 或更高版本的 Mac。

使用 Xamarin 平台不需要单独许可证。
 
可同时设置 Windows 和 Mac 计算机，在这些安装程序运行期间，可通过[了解如何使用 Xamarin 进行移动开发](../cross-platform/learn-about-mobile-development-with-xamarin.md)阅读和观看必要的背景材料。

如果在执行此设置和安装后使用 Xamarin 平台时遇到问题，请在 [ forums.xamarin.com](http://forums.xamarin.com/) 上发布。

<a name="prereq" /> 

## <a name="pre-requisites"></a>先决条件

###  <a name="for-targeting-windows-and-android"></a>若要定位 Windows 和 Android

请参阅 [Visual Studio 2017 产品系列系统要求](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs)，详细了解安装 Visual Studio 2017 的先决条件。

在操作系统为已安装所有更新的 Windows 10 的物理 Windows 计算机（不是虚拟机）上安装 Visual 2017。 

### <a name="for-targeting-ios"></a>若要定位 iOS

若要从 Windows 计算机将 iOS 仿真器和设备设为目标，还需要有运行 macOS 10.12 或更高版本和 Xcode 8.3 的联网 Mac 或 Mac mini。 请参阅[设置和安装 Visual Studio for Mac](/visualstudio/mac/installation.md)，了解详细要求。

<a name="windows" /> 

##  <a name="windows-setup-visual-studio-and-xamarin"></a>Windows 设置（Visual Studio 和 Xamarin）

如果尚未安装 Visual Studio 2017，请执行以下操作：

1.  [下载并启动 Visual Studio 2017 任意版本（Community、Professional 或 Enterprise）的安装程序](https://www.visualstudio.com/downloads/)。 Visual Studio 2017 Community 是免费版本。 Professional 和 Enterprise 版提供了为期 30 天的试用版，到期后需要许可证。

2.  出现“安装”对话框时，请选中以下选框：    

    - “移动和游戏”>“使用 .NET 的移动环境”。 此选项也将自动选择各种 Android 工具和软件开发工具包。 

        ![选择“游戏和移动开发”下的“移动开发”选项](../cross-platform/media/cross-plat-xamarin-setup-2a.png "跨平台 Xamarin 安装 2")

    - （可选）“Windows”>“通用 Windows 平台开发”。 

如果已安装 Visual Studio 2017，但尚未安装 Xamarin 平台，请执行以下操作：

1. 从“开始”菜单运行“Visual Studio 安装程序”。

2.  在安装程序中，单击“更多”按钮，然后选择“修改”:

    ![选择 Visual Studio 安装程序中的“修改”选项](../cross-platform/media/cross-plat-xamarin-setup-1a.png "跨平台 Xamarin 安装 1")

3.  出现“安装”对话框时，请选中“移动和游戏”>“使用 .NET 的移动开发”和（可选）“Windows”>“通用 Windows 平台开发”。 “使用 .NET 的移动开发”选项还应更新现有的所有 Xamarin 安装。

在运行安装时，可继续查看 Mac 安装说明并浏览[了解如何使用 Xamarin 进行移动开发](../cross-platform/learn-about-mobile-development-with-xamarin.md)。

5.  安装完成后，请启动 Visual Studio 并在系统提示时使用你的 Microsoft 帐户进行登录。 此帐户即用于 Windows 的帐户。

6.  要测试 Android 应用，请使用 [Android SDK 仿真器](/xamarin/android/get-started/installation/android-emulator/)（如果没有物理 Android 设备的话）。 

<a name="mac" />

##  <a name="mac-setup-apple-id-xcode-and-xamarin"></a>Mac 设置（Apple ID、Xcode 和 Xamarin）

1.  如果尚无 Apple ID，请在 [https://appleid.apple.com](https://appleid.apple.com/) 处创建免费 Apple ID。 安装和登录 Xcode 需要此 Apple ID。

2.  从 [https://developer.apple.com/xcode/](https://developer.apple.com/xcode/) 处下载并安装 Xcode，并如[将帐户添加到 Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com) 中所述添加你的 Apple ID。

3.  按照[设置和安装 Visual Studio for Mac](/visualstudio/mac/installation.md) 上的说明操作，下载并安装 Visual Studio for Mac。

4.  在 Windows 和 Mac 计算机上安装好 Xamarin 后，请按照[连接到 Mac](/xamarin/ios/get-started/installation/windows/connecting-to-mac/) 上的说明操作，以便可通过 Windows 计算机上的 Visual Studio 针对 iOS 和 Mac 进行开发。

这两台计算机必须位于同一本地网络。