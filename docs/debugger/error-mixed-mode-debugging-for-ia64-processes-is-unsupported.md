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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5c4414651249aa7622e7f7be59e6150a4925f1b8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60089336"
---
# <a name="error-mixed-mode-debugging-for-ia64-processes-is-unsupported"></a>错误：不支持对 IA64 进程执行混合模式调试
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 调试器不支持对基于 Itanium 的进程中的混合本机代码和托管代码进行调试。

### <a name="to-correct-this-error"></a>更正此错误

- 生成 32 位版本的应用程序以进行调试。

## <a name="see-also"></a>请参阅
- [远程调试](../debugger/remote-debugging.md)