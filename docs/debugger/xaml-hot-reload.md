---
title: 编写和调试使用 XAML 热重新加载的 XAML
description: XAML 热重新加载，或 XAML 编辑并继续，可以运行应用时对 XAML 代码进行更改
ms.custom: ''
ms.date: 02/28/2019
ms.topic: conceptual
helpviewer_keywords:
- xaml edit and continue
- xaml hot reload
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f526cc8d5ff7835b3d0b942325f5755898fad147
ms.sourcegitcommit: c6249a8f3054db881ba62f4e80bf006d440f5a2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2019
ms.locfileid: "66462139"
---
# <a name="write-and-debug-running-xaml-code-with-xaml-hot-reload-in-visual-studio"></a>编写和调试正在运行的 XAML 代码与 XAML 在 Visual Studio 中的热重新加载

Visual Studio XAML 热重新加载来帮助你通过让你对 XAML 代码进行更改，您的应用程序运行时构建 WPF 或 UWP 应用 UI。 此功能可以以增量方式生成和测试与正在运行的应用的数据上下文、 身份验证状态和其他很难在设计时期间模拟的实际复杂性的权益的 XAML 代码。

XAML 热重新加载是在这些方案中尤其有用：

* 修复 UI 问题在调试模式下启动应用程序后，在 XAML 代码中找到。

* 构建应用程序的新 UI 组件正在开发，同时利用应用程序的运行时上下文。

|支持的应用程序类型|操作系统和工具|
|-|-|-|
|Windows Presentation Foundation (WPF) |.NET Framework 4.6 及更高版本</br>Windows 7 和更高版本 |
|通用 Windows 应用 (UWP)|Windows 10 及更高版本，具有 [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 14393 + |

> [!NOTE]
> Visual Studio XAML 热重新加载目前仅支持带有附加调试程序在 Visual Studio 中运行应用程序时 (**F5**或**开始调试**)。 不能使用来启用此体验*附加到进程*。

## <a name="known-limitations"></a>已知限制

下面是已知的 XAML 限制热重新加载。 若要解决你遇到的任何限制，只需停止调试程序，然后完成该操作。

|限制|WPF|UWP|说明|
|-|-|-|-|
|将事件写入应用程序运行时的控件|不支持|不支持|请参阅错误：*确保事件失败*|
|如在应用程序页/窗口中的资源字典中创建的资源对象或*App.xaml*|不支持|支持|示例： 添加```SolidColorBrush```到资源字典中用作```StaticResource```。</br>注意:静态资源、 样式转换器和其他元素写入到的资源字典时可以是应用使用使用 XAML 热重新加载。 不支持仅创建资源。</br> 更改资源字典```Source```属性。| 
|应用运行时向项目添加新控件、 类、 windows 或其他文件|不支持|不支持|None|
|管理 NuGet 包 （添加/删除/更新包）|不支持|不支持|None|
|更改数据的绑定，使用 {x： 绑定} 标记扩展|不适用|Visual Studio 2019 和更高版本中受支持|Visual Studio 2017 或早期版本中不支持|

## <a name="error-messages"></a>错误消息

使用 XAML 热重新加载时可能遇到以下错误。

|错误消息|描述|
|-|-|-|
|确保事件失败|错误表示尝试绑定到一个控件，你的应用程序运行时不受支持的事件。|
|“XAML 编辑并继续”找不到任何要更新的元素。|错误发生时正在编辑热重新加载的 XAML 不能更新应用程序中。</br> 通过使用正在运行的应用导航到一个视图，使用 XAML 的位置，有时可以修复此错误。</br> 有时，此错误意味着不能应用特定更改，直到重新启动调试会话。 |
|调试会话期间不支持此更改。|错误指示 XAML 热重新加载不支持您尝试更改。 停止调试会话，进行更改，然后重新启动调试会话。|
