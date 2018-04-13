---
title: 将专用网络中的 URL 列入允许列表 | Microsoft Docs
ms.custom: ''
ms.date: 09/19/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4a4093c7ebba74493a64833bfbf83ee6d28ef1ef
ms.sourcegitcommit: 06cdc1651aa7f45e03d260080da5a623d6258661
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="whitelisting-urls-in-a-private-network"></a>将专用网络中的 URL 列入允许列表

如果在使用防火墙等安全设备的专用网络中使用 Visual Studio，则 Visual Studio 可能无法连接到某些网络资源。 这些资源包括用于登录和授权的 Visual Studio Team Services (VSTS)、NuGet 和 Azure 服务。 如果 Visual Studio 无法连接到上述某个资源，则会出现以下错误消息：

  **基础连接已关闭：发送时出现意外错误**

Visual Studio 使用传输层安全性 (TLS) 1.2 协议连接到网络资源。 Visual Studio 使用 TLS 1.2 时，某些专用网络上的安全设备会阻止某些服务器连接。 要修复此错误，请对以下 URL 启用连接：

- https://management.core.windows.net

- https://app.vssps.visualstudio.com

- https://login.microsoftonline.com

- https://login.live.com

- https://go.microsoft.com

- https://graph.windows.net

- https://app.vsspsext.visualstudio.com

- *.azurewebsites.net（用于 Azure 连接）

- *.nuget.org（用于 NuGet 连接）

- *.visualstudio.com

- cdn.vsassets.io（主机内容传送网络或 CDN、内容）

- *.gallerycdn.vsassets.io（主机 VSTS 扩展）

- static2.sharepointonline.com（Visual Studio 在字体等 office fabric UI 工具包中使用的主机资源）

> [!NOTE]
> 上述列表中可能未包含私人拥有的 NuGet 服务器 URL。 你可以打开 %APPData%\Nuget\NuGet.Config 来检查正在使用的 NuGet 服务器。

## <a name="see-also"></a>请参阅

[代理身份验证所需的错误](../ide/reference/proxy-authorization-required.md)  
[在防火墙或代理服务器后安装 Visual Studio](../install/install-visual-studio-behind-a-firewall-or-proxy-server.md)
