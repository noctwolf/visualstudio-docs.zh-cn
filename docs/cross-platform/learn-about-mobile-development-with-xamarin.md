---
title: 了解如何使用 Xamarin 进行移动开发 | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: e970d936-1df4-4c0c-96e3-ef6191295882
ms.prod: xamarin
ms.technology: xamarin-tools
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 921faa49690b641fda0e864d27705040a1b97f1e
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="learn-about-mobile-development-with-xamarin"></a>了解关于使用 Xamarin 进行移动开发的信息

本文列出的几个概述有助于了解如何使用 Xamarin 开发跨平台移动个应用。 如果尚未安装 Visual Studio 和 Xamarin，请首先启动 [Setup and install](../cross-platform/setup-and-install.md) 过程，然后在安装程序运行期间返回此处浏览这些资源。  
  
> [!NOTE]
> 除非另有说明，建议刚开始仅浏览此处链接直接指向的页面，而不浏览其子页面。 如果完成此列表后安装过程仍在运行，请随意返回浏览其他主题。  
>   
> 还可随意查看标记为“基础知识”的主题，并在稍后返回到“深入了解”主题。  
  
## <a name="essentials-introduction-to-xamarin"></a>基础知识：Xamarin 简介  

*10-20 分钟*  
  
1.  [通过 Xamarin 在 Visual Studio 中构建移动应用](https://www.visualstudio.com/xamarin/) (visualstudio.com) 概括地介绍了 Xamarin 的主要特征。  
  
2.  与 Xamarin 推广人员 James Montemagno 一起[使用 C# 和 Visual Studio 生成跨平台移动应用](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2015-Final-Release-Event/Building-cross-platform-mobile-apps-using-C-and-Visual-Studio-2015) （第 9 频道，15 分 16 秒）。 前三分钟是 Xamarin 概述，接着是代码演示。  
  
## <a name="essentials-overview-of-the-visual-studio-and-xamarin-environment"></a>基础知识：Visual Studio 和 Xamarin 环境概述  

*5-15 分钟*  
  
-   将使用安装了 Visual Studio 和 Xamarin 的 Windows 计算机完成大部分工作。 将在此计算机上直接构建 Windows 和 Android 应用，然后在桌面、设备或模拟器上运行和调试这些应用。 还可通过 Mac 远程生成、运行和调试 iOS 应用。 Windows 计算机上的 Visual Studio 还可连接到 iOS 情节提要设计器和 iOS 模拟器。  
  
-   安装了 Xcode 和 Visual Studio for Mac 的 Mac 将作为 iOS 应用的生成主机、签名主机和运行时环境。 Windows 计算机委托在这台 Mac 上生成 iOS 应用。 应用程序在 Mac 上的 iOS 模拟器上运行，或直接在连接到 Mac 的受限设备上运行。 可在 Mac 上与该应用交互，但需在 Visual Studio 中调试体验。
  
下图展示了各方之间的关系。  
  
![Xamarin 环境中 Windows 与 Mac 开发计算机之间的关系](../cross-platform/media/crossplat-xamarin-learn-1.png "CrossPlat Xamarin Learn 1")  

> [!NOTE]
> 出于完整性的考虑在此图中显示了 Windows Phone。 使用 Xamarin 平台时，推荐选择 .NET Standard 2.0 库进行代码共享，因为它与 Windows Phone 或 Windows 10 移动设备不兼容。 

请参阅 [ Xamarin.iOS for Visual Studio 简介](/xamarin/ios/get-started/installation/windows/introduction-to-xamarin-ios-for-visual-studio/)，了解有关生成 iOS 应用的详细信息。
  
## <a name="essentials-how-projects-are-structured"></a>基础知识：如何构造项目  

*10-30 分钟*  
  
1.  [共享代码选项](/xamarin/cross-platform/app-fundamentals/code-sharing/)。 若是新应用程序，应使用 .NET Standard 库共享代码。 大多数业务逻辑代码将驻留在 .NET Standard 库中，包括对数据库的访问、对 REST API 的调用和对可移植 Xamarin 组件的调用。 （请参阅本文末尾的[深入了解：Xamarin 组件](#components)）。 使用 Xamarin.Forms 编写的常见 UI 代码也驻留在 .NET Standard 库中。  
  
2.  （选读）[案例研究：Tasky](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/case-study-tasky/) 介绍了设计和构造功能齐全的应用的一些最佳做法，例如使用分隔数据、数据访问和业务层的共享代码构造项目。  
  
## <a name="essentials-native-and-xamarinforms-ui-layers"></a>基础知识：本机与 Xamarin.Forms UI 层  

*10-40 分钟*  
  
Xamarin 提供了两种方法来生成卓越的应用：Xamarin 本机与 Xamarin.Forms。  
  
Xamarin 本机可用于为每个目标平台（iOS、 Android 和 Windows）编写单独的 UI 代码。  使用此方法可以直接访问特定于平台的 API，从而为每个平台设计自定义 UI 体验。  你还具有对每个平台的本机设计器和控件的完全访问权限，此权限有助于构建相应 UI。  
  
Xamarin.Forms 提供了一组通用 API，借助它可以在一个 .NET Standard 库中为所有平台编写共享 UI 层。  Xamarin.Forms 将向每个目标平台呈现本机控件，以提供本机观感。  将使用 C# 和 XAML（而不是设计器）生成 UI。  

大多数开发人员使用 Xamarin.Forms。 建议刚开始使用 Xamarin 的开发人员使用这种方法。 Xamarin 本机方法比较困难，并需要对目标平台有更详细的了解。
  
无需预先决定使用哪种方法；可以使用 Xamarin 本机与 Xamarin.Forms 的组合来实现应用：  
  
-   使用 Xamarin.Forms 生成通用屏幕。 通用屏幕可以跨平台提供类似的用户界面和功能，例如登录、联系人窗体和搜索结果。  
  
-   使用 Xamarin.Forms 中的各种自定义功能根据每个平台调整 UI。 最简单的自定义选项是使用 `OnPlatform` API。 还可以创建自定义视图、扩展现有呈现器以及创建自定义呈现器。  
  
-   需要时可使用 Xamarin 本机构建采用每个平台的独特 UI 特性的屏幕。 例如，使用本机相机捕获和图像操作的屏幕。  
  
一般而言，最开始应使用 Xamarin.Forms 解决方案建立跨平台 UI 代码共享。 然后使用自定义功能进行特定于平台的调整。 如果需要完全特定于平台的屏幕，你可以使用 Xamarin 本机单独添加它们。  
  
了解更多信息：  
  
1.  [Xamarin.Forms](/xamarin/xamarin-forms/) 简要概述了 Xamarin.Forms 与本机 UI 层（即 Xamarin.iOS 和 Xamarin.Android），并分析了各自的利弊。  
  
2.  James Montemagno 的视频 [Xamarin.Forms：使用 C# 和 XAML 创建本机 iOS、Android 和 Windows 应用](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/704)（第 9 频道，13 分 3 秒）前三分钟提供了另一个概述，也可继续观看演示。  
  
3.  （选读）[Xamarin.Forms 简介](/xamarin/xamarin-forms/get-started/introduction-to-xamarin-forms/)  
  
4.  （选读）在[设备类](/xamarin/xamarin-forms/platform/device/)文档中查看使用 `OnPlatform` 进行自定义的示例
  
5.  （选读）由 MSDN 杂志的 Jason Smith 撰写的 [跨平台 - 通过 Xamarin.Forms 跨移动平台共享 UI 代码](https://msdn.microsoft.com/magazine/dn904669.aspx) 概括了 Xamarin.Forms 中的各个自定义选项，其中 [自定义呈现器](/xamarin/xamarin-forms/app-fundamentals/custom-renderer/)介绍了其详细信息。  
  
## <a name="deeper-dive-debugging-with-emulators"></a>深入了解：使用模拟器进行调试  

*10-15 分钟*  
  
若要在不使用物理设备的情况下调试跨平台应用程序，则需要使用以下模拟器：  
  
### <a name="microsofts-android-emulator"></a>Microsoft 的 Android 模拟器 

建议使用随 Visual Studio 一起安装的 Microsoft 的[适用于 Android 的 Visual Studio 模拟器](visual-studio-emulator-for-android.md)。  [Visual Studio Android 模拟器](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/711) 视频（第 9 频道，5 分 55 秒）提供了相关概述与演示。  
  
### <a name="apples-ios-simulator"></a>Apple 的 iOS 模拟器

若要了解详细信息，请参阅 [iOS 模拟器入门](https://developer.apple.com/library/prerelease/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html#//apple_ref/doc/uid/TP40012848-CH5-SW1) (apple.com)。  
  
### <a name="microsofts-windows-phone-emulator"></a>Microsoft 的 Windows Phone 模拟器。

要了解详细信息，请参阅[使用适用于 Windows 10 移动版的 Microsoft 模拟器进行测试](/windows-uwp/windows-apps-src/debug-test-perf/test-with-the-emulator/)。  
  
<a name="components" /> 

## <a name="deeper-dive-xamarin-components"></a>Deeper Dive: Xamarin Components  

*10 分钟*  
  
Xamarin 应用可通过 Xamarin 组件使用许多扩展功能。 可以在 [http://components.xamarin.com/](http://components.xamarin.com/) 上下载完整目录，其中包括其他 UI 控件、身份验证和 Microsoft Azure 等各种云服务以及其他更多部分。