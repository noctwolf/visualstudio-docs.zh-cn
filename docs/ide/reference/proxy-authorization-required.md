---
title: "所需的代理授权错误 | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6544edb62bac07f5ab787e4a3b2f8abaebafa777
ms.sourcegitcommit: cc288456329aefca1fdaa7ce74751ce195985c14
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="proxy-authorization-required"></a>所需的代理身份验证

当用户通过代理服务器连接到 Internet，而代理服务器阻止 Visual Studio 对某些网络资源进行的调用时，通常会发生此错误。

## <a name="to-correct-this-error"></a>更正此错误

- 重新启动 Visual Studio。 这时会出现一个代理身份验证对话框。 在对话框中输入你的凭据。

- 如果上述步骤未能解决问题，这可能是由于你的代理服务器不提示需要提供 http://go.microsoft.com 地址的凭据，而是提示需要 *.visualStudio.com 地址的凭据。 对于这些服务器，需要将以下 URL 列表列入到允许列表，以便取消对 Visual Studio 中所有登录方案的阻止：

    - *.windows.net

    - *.microsoftonline.com

    - *.visualstudio.com

    - *.microsoft.com

    - *.live.com

- 否则，可以从允许列表中删除 http://go.microsoft.com address 地址，以便在重启 Visual Studio 时，会对 http://go.microsoft.com 地址和服务器终结点出现代理身份验证对话框。

    或

- 如果你想通过代理使用默认凭证，可以执行以下操作：

    1. 查找 devenv.exe.config（devenv.exe 配置文件），查找位置为：%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE 或 %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE。

    1. 在配置文件中查找 `<system.net>` 块，并添加这个代码：

        ```xml
        <defaultProxy enabled="true" useDefaultCredentials="true">
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
        </defaultProxy>
        ```

        你必须在 `proxyaddress="<http://<yourproxy:port#>`中为你的网络插入正确的代理地址。

    或

- 你也可以按 [此帖子](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) 上的说明添加允许你使用代理的代码。

## <a name="see-also"></a>请参阅

[Visual Studio 使用的 Internet 资源](../connected-environment.md)