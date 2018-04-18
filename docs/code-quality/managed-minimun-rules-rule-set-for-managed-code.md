---
title: 托管最少量规则规则的托管代码设置 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 6c14af4c569749273b6ed6b73fe48249df3f1ee0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="managed-minimum-rules-rule-set-for-managed-code"></a>托管最少量规则的规则集托管代码
托管最少量规则侧重于在代码中，包括潜在的安全漏洞、 应用程序崩溃和其他重要的逻辑和设计错误的最关键问题。 应包括在任何自定义规则集中设置为你的项目创建此规则。  
  
|规则|描述|  
|----------|-----------------|  
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|具有可释放字段的类型应该是可释放的|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|移除空终结器|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|应释放可释放的字段|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|重写 ValueType.Equals 时应重载相等运算符|
