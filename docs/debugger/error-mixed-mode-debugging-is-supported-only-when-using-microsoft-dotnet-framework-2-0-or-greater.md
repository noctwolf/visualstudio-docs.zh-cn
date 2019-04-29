---
title: 错误：仅在使用 Microsoft.NET Framework 2.0 或更高版本支持混合的模式调试 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2fb4d0dfaeb944700757c9ceec222dbd62dab9dd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850681"
---
# <a name="error-mixed-mode-debugging-is-supported-only-when-using-microsoft-net-framework-20-or-greater"></a>错误：仅当使用 Microsoft .NET Framework 2.0 或更高版本时，才支持混合模式调试
若要调试混合的本机代码和托管代码，必须安装有 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0、3.0、 3.5 或 4 版。 早期版本的 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 不支持混合模式调试。

### <a name="to-correct-this-error"></a>更正此错误

- 将 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 升级到 2.0、3.0、3.5 或 4 版。

## <a name="see-also"></a>请参阅
- [远程调试](../debugger/remote-debugging.md)