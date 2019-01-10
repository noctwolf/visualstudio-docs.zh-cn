---
title: 错误：不支持混合的模式调试的 IA64 进程 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_ia64
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 56df416b7142e0ff9f7e96b8c1b2cba6e73b65a9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916767"
---
# <a name="error-mixed-mode-debugging-for-ia64-processes-is-unsupported"></a>错误：不支持对 IA64 进程执行混合模式调试
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 调试器不支持对基于 Itanium 的进程中的混合本机代码和托管代码进行调试。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   生成 32 位版本的应用程序以进行调试。  
  
## <a name="see-also"></a>请参阅  
 [Remote Debugging](../debugger/remote-debugging.md)