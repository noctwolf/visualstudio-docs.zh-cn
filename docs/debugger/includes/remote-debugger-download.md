---
title: 远程调试器下载
description: 远程调试器的下载链接
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 01ec01ad642333d9ee46296cbcb4a02526152e94
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526868"
---
在远程设备或服务器，你想要调试，而非 Visual Studio 计算机，下载并安装远程工具的正确版本从下表中的链接。

- 下载最新版本的 Visual Studio 远程工具。 最新的远程工具版本兼容使用早期的 Visual Studio 版本，但早期的远程工具版本不是与更高版本的 Visual Studio 版本兼容。
- 下载的远程工具使用相同的体系结构在计算机安装它们。 例如，如果你想要调试远程计算机运行 64 位操作系统上的 32 位应用程序，安装 64 位远程工具。

::: moniker range=">=vs-2019"

> [!NOTE]
> 直到 Visual Studio 2019 独立远程工具都可用时，如果您需要使用 Visual Studio 2019，使用远程调试器[查找远程调试器](https://docs.microsoft.com/visualstudio/debugger/remote-debugging?view=vs-2017#fileshare_msvsmon)的 Visual Studio 2019，并安装中复制和上运行您的远程计算机或从文件共享上运行。

::: moniker-end

|Version|链接|说明|
|-|-|-|
|Visual Studio 2017（最新版本）|[远程工具](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|与所有 Visual Studio 2017 版本兼容。 下载匹配您设备的操作系统 (x 86、 x64、 或 ARM64） 的版本。 在 Windows 服务器上，请参阅[取消阻止文件下载](../../debugger/remote-debugging-unblock-file-download.md)下载远程工具的帮助。|
|Visual Studio 2015|[远程工具](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Visual Studio 2015 远程工具可从 My.VisualStudio.com。 如果系统提示，请加入免费[Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/)程序或使用 Visual Studio 订阅 id。 登录 在 Windows 服务器上，请参阅[取消阻止文件下载](../../debugger/remote-debugging-unblock-file-download.md)下载远程工具的帮助。|
|Visual Studio 2013|[远程工具](/previous-versions/visualstudio/visual-studio-2013/bt727f1t(v=vs.120)#Installing_the_Remote_Tools)|下载 Visual Studio 2013 文档中的页|
|Visual Studio 2012|[远程工具](/previous-versions/visualstudio/visual-studio-2012/bt727f1t(v=vs.110)#BKMK_Installing_the_Remote_Tools)|下载 Visual Studio 2012 文档中的页|

复制可运行远程调试器*msvsmon.exe*到远程计算机，而不是安装远程工具。 但是，远程调试器配置向导 (*rdbgwiz.exe*) 可仅当安装远程工具。 您可能需要使用该向导进行配置，如果你想要远程调试器作为服务运行。 有关详细信息，请参阅[（可选） 配置远程调试器作为服务](../../debugger/remote-debugging.md#bkmk_configureService)。

>[!NOTE]
>- 若要调试 ARM 设备上的 Windows 10 应用，使用 ARM64，这是可用的远程工具的最新版本。
>- 若要调试在 Windows RT 设备上的 Windows 10 应用，使用 ARM，仅在 Visual Studio 2015 远程工具下载中可用。
