---
title: 错误： 混合模式调试支持对 x64 进程是仅当使用 Microsoft.NET Framework 4 或更高版本 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: d5550383d1d5882d8824ce2d282b2035882cdcef
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>错误：仅当使用 Microsoft .NET Framework 4 或更高版本时才支持对 x64 进程执行混合模式调试
若要调试 64 位进程中的混合本机代码和托管代码，您必须安装了 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4 版。 低于 4 的 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 版本不支持对 64 位进程进行混合模式调试。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   执行以下步骤之一：  
  
    -   将 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 升级到 4 版。  
  
    -   生成 32 位版本的应用程序以进行调试。  
  
## <a name="see-also"></a>请参阅  
 [远程调试](../debugger/remote-debugging.md)