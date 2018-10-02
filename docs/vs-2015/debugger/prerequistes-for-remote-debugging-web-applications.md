---
title: 远程调试 Web 应用程序的必备组件 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications, remote servers
- remote debugging, prerequisites
- remote servers, debugging Web applications
ms.assetid: 1cd777b5-6d20-4ca6-a0df-51653b118469
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 197a6e9b433173f1de13e3506db79e7edf53bade
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477871"
---
# <a name="prerequistes-for-remote-debugging-web-applications"></a>远程调试 Web 应用程序的必备组件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[远程调试 Web 应用程序的必备组件](https://docs.microsoft.com/visualstudio/debugger/prerequistes-for-remote-debugging-web-applications)。  
  
使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 调试器，您可以在本地计算机或远程服务器上以透明方式调试 Web 应用程序。 这意味着，调试器始终以相同的方式运行，因而允许您在任一计算机上使用相同的功能。 但若要使远程调试正常进行，有一些先决条件。  
  
-   必须在要调试的服务器上安装 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 远程调试组件。 有关详细信息，请参阅[设置远程调试](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)。  
  
-   默认情况下，[!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程作为 ASPNET 用户进程运行。 因此，您必须在运行 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 的计算机上拥有管理员特权，才能对其进行调试。 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程的名称因调试方案和 IIS 版本而异。 有关详细信息，请参阅 [How to: Find the Name of the ASP.NET Process](../debugger/how-to-find-the-name-of-the-aspnet-process.md)。  
  
## <a name="see-also"></a>请参阅  
 [调试 ASP.NET 和 AJAX 应用程序](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [系统要求](../debugger/aspnet-debugging-system-requirements.md)



