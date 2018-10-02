---
title: 错误： web 服务器配置不正确 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82d827e0f821712306cf1ec6049129fbf4437d67
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483277"
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>错误：Web 服务器配置不正确
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[错误： web 服务器配置不正确](https://docs.microsoft.com/visualstudio/debugger/error-the-web-server-is-not-configured-correctly)。  
  
此错误的可能原因包括：  
  
-   尝试调试一个已复制到不同的计算机上、经过手动重命名或移动过的 .NET Web 应用程序。  
  
-   没有足够的 IIS 连接。 有关将网站部署到 IIS 的详细信息，请参阅 [创建网站](http://www.iis.net/learn/get-started/getting-started-with-iis/create-a-web-site)。  
  
-   如果想要调试 ASP.NET 应用程序，请参阅[发布到 IIS](https://docs.asp.net/en/latest/publishing/iis.html)有关部署到运行 IIS 8 或更高版本，远程计算机的说明或[Remote Debugging ASP.NET on a Remote IIS 7.5 Computer](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)有关部署到运行 IIS 7.5 的远程计算机的说明。  
  
## <a name="see-also"></a>请参阅  
 [调试 Web 应用程序：错误和疑难解答](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



