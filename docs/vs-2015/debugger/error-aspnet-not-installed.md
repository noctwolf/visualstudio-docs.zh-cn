---
title: 错误：未安装 ASP.NET |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e60fe59b4d515f37593175f0b76d1562f170abfb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60059092"
---
# <a name="error-aspnet-not-installed"></a>错误：未安装 ASP.NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

当您尝试调试的计算机上未正确安装 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 时，会发生此错误。 此错误可能意味着从未安装 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]，或者先安装了 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]，然后又安装了 IIS。  
  
### <a name="to-reinstall-aspnet"></a>重新安装 ASP.NET  
  
1. 从命令提示符窗口中，运行以下命令：  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     *版本*表示你的计算机中安装的 .NET Framework 的版本号，例如 v1.0.370。 你可以通过查看`\WINDOWS\Microsoft.NET\Framework` 目录确定的 Framework 版本。  
  
    > [!NOTE]
    >  对于 Windows Server 2003，可以通过在控制面板中使用**添加或删除程序**安装[!INCLUDE[vstecasp](../includes/vstecasp-md.md)]。  
  
## <a name="see-also"></a>请参阅  
 [调试 Web 应用程序：错误和疑难解答](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
