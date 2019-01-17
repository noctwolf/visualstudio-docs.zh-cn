---
title: 错误：未安装 ASP.NET |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.http_not_supported
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 41ec708b25bc74eb1f566981ee4bbcdc23827087
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "53902083"
---
# <a name="error-aspnet-not-installed"></a>错误：未安装 ASP.NET
当您尝试调试的计算机上未正确安装 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 时，会发生此错误。 此错误可能意味着从未安装 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]，或者先安装了 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]，然后又安装了 IIS。  
  
### <a name="to-reinstall-aspnet"></a>重新安装 ASP.NET  
  
1. 从命令提示符窗口中，运行以下命令：  
  
   ```cmd
   \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
   ```  
  
    *版本*表示你的计算机中安装的 .NET Framework 的版本号，例如 v1.0.370。 你可以通过查看`\WINDOWS\Microsoft.NET\Framework` 目录确定的 Framework 版本。  
  
   > [!NOTE]
   >  对于 Windows Server 2003，可以使用控制面板中的“添加/删除程序”来安装 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]。  
  
## <a name="see-also"></a>请参阅  
 [调试 Web 应用程序：错误和疑难解答](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
