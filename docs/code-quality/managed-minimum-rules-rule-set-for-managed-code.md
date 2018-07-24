---
title: 设置托管代码的托管最少量规则规则
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: bf05f4787cbd393173380be8123657abeddc0cd5
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204505"
---
# <a name="managed-minimum-rules-rule-set-for-managed-code"></a>设置托管代码的托管最少量规则规则

托管最少量规则专注于在代码中，包括潜在安全漏洞、 应用程序崩溃和其他重要的逻辑和设计错误的最关键问题。 创建包含此规则设置任何自定义规则集中你为你的项目。

|规则|描述|
|----------|-----------------|
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|具有可释放字段的类型应该是可释放的|
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|移除空终结器|
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|应释放可释放的字段|
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|重写 ValueType.Equals 时应重载相等运算符|
