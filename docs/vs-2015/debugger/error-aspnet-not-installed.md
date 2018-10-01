---
title: 错误： 未安装 ASP.NET |Microsoft Docs
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
- vs.debug.error.http_not_supported
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
ms.assetid: 6286dd3d-3e2b-4edd-959d-81e0ed45500b
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0617f5200a69809afc86fe9405dc3ea9bd8fcda0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479658"
---
# <a name="error-aspnet-not-installed"></a>错误：未安装 ASP.NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[错误： 未安装 ASP.NET](https://docs.microsoft.com/visualstudio/debugger/error-aspnet-not-installed)。  
  
当您尝试调试的计算机上未正确安装 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 时，会发生此错误。 此错误可能意味着从未安装 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]，或者先安装了 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]，然后又安装了 IIS。  
  
### <a name="to-reinstall-aspnet"></a>重新安装 ASP.NET  
  
1.  从命令提示符窗口中，运行以下命令：  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     其中*版本*表示您的计算机，例如，v1.0.370 上安装的.NET Framework 的版本号。 你可以通过查看确定的 framework 版本`\WINDOWS\Microsoft.NET\Framework`目录。  
  
    > [!NOTE]
    >  对于 Windows Server 2003，可以安装[!INCLUDE[vstecasp](../includes/vstecasp-md.md)]通过使用**添加或删除程序**控制面板中。  
  
## <a name="see-also"></a>请参阅  
 [调试 Web 应用程序：错误和疑难解答](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



