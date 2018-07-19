---
title: 错误： 未安装 ASP.NET |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: fd660ea2cdeaaae5d37811406221a7d150ab9bef
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056656"
---
# <a name="error-aspnet-not-installed"></a>错误：未安装 ASP.NET
当您尝试调试的计算机上未正确安装 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 时，会发生此错误。 此错误可能意味着从未安装 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]，或者先安装了 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]，然后又安装了 IIS。  
  
### <a name="to-reinstall-aspnet"></a>重新安装 ASP.NET  
  
1.  从命令提示符窗口中，运行以下命令：  
  
    ```cmd
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     其中*版本*表示您的计算机，例如，v1.0.370 上安装的.NET Framework 的版本号。 你可以通过查看确定的 framework 版本`\WINDOWS\Microsoft.NET\Framework`目录。  
  
    > [!NOTE]
    >  对于 Windows Server 2003，可以安装[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]通过使用**添加或删除程序**控制面板中。  
  
## <a name="see-also"></a>请参阅  
 [调试 Web 应用程序：错误和疑难解答](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
