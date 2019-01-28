---
title: CA1707:标识符不应包含下划线
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotContainUnderscores
- CA1707
helpviewer_keywords:
- CA1707
- IdentifiersShouldNotContainUnderscores
ms.assetid: 5fb539ef-c304-4323-90c0-b14386da9774
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bb7fc19f90b7f0cd329dd1cff972d08c2052b055
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54951373"
---
# <a name="ca1707-identifiers-should-not-contain-underscores"></a>CA1707:标识符不应包含下划线

|||
|-|-|
|TypeName|IdentifiersShouldNotContainUnderscores|
|CheckId|CA1707|
|类别|Microsoft.Naming|
|是否重大更改|-对程序集引发时中断<br /><br /> 无间断-类型参数上发生|

## <a name="cause"></a>原因

标识符名称包含下划线 (\_) 字符。

## <a name="rule-description"></a>规则说明

按照约定，标识符名称不包含下划线 (\_) 字符。 此规则检查命名空间、 类型、 成员和参数。

命名约定提供了通用的外观对于库面向公共语言运行时。 这会减少所需的新软件库，并会增加客户信心库由必须在托管代码中开发的专业知识的人学习曲线。

## <a name="how-to-fix-violations"></a>如何解决冲突

从名称中删除所有下划线字符。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。

## <a name="related-rules"></a>相关的规则

- [CA1709:标识符应采用正确的大小写](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708:标识符不应不同于用例的详细信息](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
