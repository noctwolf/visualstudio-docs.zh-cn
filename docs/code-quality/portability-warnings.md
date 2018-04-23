---
title: 可移植性警告
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
ms.openlocfilehash: e6fe3bcd703d7fd58d5590b755a553d8ead4c0a9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="portability-warnings"></a>可移植性警告
可移植性警告支持跨不同操作系统的可移植性。

## <a name="in-this-section"></a>本节内容

|规则|描述|
|----------|-----------------|
|[CA1900：值类型字段应为可移植字段](../code-quality/ca1900-value-type-fields-should-be-portable.md)|此规则检查： 当用显式布局特性声明的结构封送到 64 位操作系统上的非托管代码时，将是否正确对齐。|
|[CA1901: P/Invoke 声明应为可移植](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|此规则计算 P/Invoke，返回值和每个参数的大小，并验证它们的大小正确封送到 32 位和 64 位操作系统上的非托管代码时。|
|[CA1903：仅使用目标框架中的 API](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|一个成员或类型使用了某个 Service Pack 中引入的成员或类型，该 Service Pack 没有与项目的目标框架一起包括。|