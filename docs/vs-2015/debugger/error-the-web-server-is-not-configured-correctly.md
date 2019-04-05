---
title: 错误：Web 服务器未正确配置 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.remote.projnotconfigured
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 875ba87f-c372-4126-8fe3-e33931cf26c0
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c8579f54eea636f0c3ad61a28ad1e3c6d001da65
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "58937969"
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>错误：Web 服务器配置不正确
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

此错误的可能原因包括：  
  
-   尝试调试一个已复制到不同的计算机上、经过手动重命名或移动过的 .NET Web 应用程序。  
  
-   没有足够的 IIS 连接。 有关将网站部署到 IIS 的详细信息，请参阅 [创建网站](http://www.iis.net/learn/get-started/getting-started-with-iis/create-a-web-site)。  
  
-   如果你正尝试调试 ASP.NET 应用程序，请参阅 [发布到 IIS](https://docs.asp.net/en/latest/publishing/iis.html) ，了解有关部署到运行 IIS 8 或更高版本的远程计算机的说明，或参阅 [Remote Debugging ASP.NET on a Remote IIS 7.5 Computer](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md) ，了解有关部署到运行 IIS 7.5 的远程计算机的说明。  
  
## <a name="see-also"></a>请参阅  
 [调试 Web 应用程序：错误和疑难解答](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
