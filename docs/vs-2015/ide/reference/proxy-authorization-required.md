---
title: 所需的代理身份验证 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b0c197a15962d12e101e0d3ab164d706375620d9
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "59648242"
---
# <a name="proxy-authorization-required"></a>所需的代理身份验证
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

当用户通过代理服务器连接到 Visual Studio Online，而代理服务器对调用进行阻止时通常会发生此错误。 Visual Studio Online 用于使用户保持登录到 IDE 的状态。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   重新启动 Visual Studio。 这时会出现一个代理身份验证对话框。 在对话框中输入你的凭据。  
  
-   如果上述步骤未能解决问题，这可能是由于你的代理服务器不提示需要提供 http://go.microsoft.com 地址的凭据，而是提示需要 *.visualStudio.com 地址的凭据。 对于这些服务器，需要将以下列表列入到允许列表，以便取消对 Visual Studio 中所有登录方案的阻止：  
  
    -   *.windows.net  
  
    -   *.microsoftonline.com  
  
    -   *.visualstudio.com  
  
    -   *.microsoft.com  
  
    -   *.live.com  
  
-   否则，可以删除 http://go.microsoft.com地址从允许列表，以便同时显示代理身份验证对话框 http://go.microsoft.com地址和服务器终结点时重新启动 Visual Studio。  
  
-   或  
  
-   如果你想通过代理使用默认凭证，可以执行以下操作：  
  
    1.  查找 devenv.exe.config（devenv.exe 配置文件），查找位置为： **%ProgramFiles%\Microsoft Visual Studio 14.0\Common7\IDE** （或 **%ProgramFiles(x86)%\Microsoft Visual Studio 14.0\Common7\IDE**）。  
  
    2.  在配置文件中查找 `<system.net>` 块，并添加这个代码：  
  
        ```xml  
        <defaultProxy enabled="true" useDefaultCredentials="true">  
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>  
        </defaultProxy>  
  
        ```  
  
         你必须在 `proxyaddress="<http://<yourproxy:port#>`中为你的网络插入正确的代理地址。  
  
-   或  
  
-   你也可以按 [此帖子](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) 上的说明添加允许你使用代理的代码。
