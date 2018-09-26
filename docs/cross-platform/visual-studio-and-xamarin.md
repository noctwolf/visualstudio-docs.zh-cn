---
title: Visual Studio 和 Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 1da4064f-af69-472c-8f31-98484be5f790
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: caf1ea462cc69366f11e4768003707e9cc263327
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495734"
---
# <a name="visual-studio-and-xamarin"></a>Visual Studio 和 Xamarin

Xamarin 是一个移动应用开发平台，用于通过常见的 C#/.NET 代码基构建本机 iOS、Android 和 Windows 应用。 使用 Xamarin 编写的应用可在平台间实现 75% 到将近 100% 的代码重用。 这些应用对基础平台 API 具有完全访问权限并且可以合并本机用户界面。 它们编译为特定于平台的包，对运行时性能几乎没有影响。 （注意：Xamarin 也支持 F#，但本文档将仅着重介绍 C#。 此时不支持 Visual Basic。）

熟悉 C#、.NET 和 Visual Studio 的开发人员在使用 Xamarin 编写移动应用时会感受到无差别的功能和工作效率。 这些权益包括在 Android、iOS 和 Windows 设备上进行远程调试，无需学习本机编程语言（例如 Objective-C 或 Java）。 因此，许多具有精美用户界面的高性能应用（例如 NASCAR、Aviva 和 MixRadio）都是使用 Xamarin 生成的，也就不足为奇了。

本文档将帮助你利用 Xamarin 构建这些体验来评估 Visual Studio 的完整功能。

-   从 [Setup and install](../cross-platform/setup-and-install.md)开始，这一进程将花费一些时间（通常是 2-4 小时，具体取决于 Internet 连接速度、已安装内容和所选选项）。

-   在安装程序运行期间，可参阅[了解如何使用 Xamarin 进行移动开发](learn-about-mobile-development-with-xamarin.md)，该文章将介绍什么是 Xamarin 的本质并对 Xamarin.Forms 和本机 UI 进行比较等。

-   安装完成后，请[验证 Xamarin 环境](../cross-platform/verify-your-xamarin-environment.md)。

-   通过完成教程[学习在 Visual Studio 中使用 Xamarin.Forms 生成应用的基础知识](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md)完成操作。

可通过[任意版本的 Visual Studio 2017](https://visualstudio.microsoft.com/vs)（Community、Professional 和 Enterprise）使用所有 Xamarin 功能。 不需要单独的许可证。

> [!NOTE]
>  对具有 Windows 和 Visual Studio 知识的开发人员而言，这些说明描述了最简单易行的计算机配置。 使用此配置，简化了整体开发体验，因为只需与 Mac 交互即可使用 iOS 模拟器和受限设备。 如果你熟知 Mac，建议在 Parallels 或 VMWare 中运行 Visual Studio 或使用 Visual Studio for Mac。 相关说明，请参阅 [Mac 用户的设置、安装和验证](../cross-platform/setup-install-and-verifications-for-mac-users.md)。

> [!NOTE]
>  如果在寻找基于 HTML 和 CSS 的跨平台开发解决方案，请参阅 [Visual Studio 中的跨平台开发](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#HTML)中所述的用于 Apache Cordova 的 Visual Studio Tools。