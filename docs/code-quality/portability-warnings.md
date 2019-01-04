---
title: 可移植性警告
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- vs.codeanalysis.PortabilityRules
helpviewer_keywords:
- portability warnings
- managed code analysis warnings, portability warnings
- warnings, portability
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f181411d8379c8583057419c2a31f6b27c9d884
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53882450"
---
# <a name="portability-warnings"></a>可移植性警告
可移植性警告支持跨不同操作系统的可移植性。

## <a name="in-this-section"></a>本节内容

|规则|描述|
|----------|-----------------|
|[CA1900:值类型字段应为可移植](../code-quality/ca1900-value-type-fields-should-be-portable.md)|此规则检查： 当用显式布局特性声明的结构封送到 64 位操作系统上的非托管代码时，将正确对齐。|
|[CA1901:P/Invoke 声明应为可移植](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|此规则计算每个参数的大小和 P/Invoke 的返回值，并验证它们的大小正确封送到 32 位和 64 位操作系统上的非托管代码时。|
|[CA1903:使用仅目标框架中的 API](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|一个成员或类型使用了某个 Service Pack 中引入的成员或类型，该 Service Pack 没有与项目的目标框架一起包括。|