---
title: CA1707：标识符不应包含下划线
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 36ced0a2ef262a274931e3a17236da11e894f393
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca1707-identifiers-should-not-contain-underscores"></a>CA1707：标识符不应包含下划线
|||
|-|-|
|TypeName|IdentifiersShouldNotContainUnderscores|
|CheckId|CA1707|
|类别|Microsoft.Naming|
|是否重大更改|-在程序集上引发时中断<br /><br /> 无间断-如果是针对类型参数引发|

## <a name="cause"></a>原因
 标识符名称包含下划线 (_) 字符。

## <a name="rule-description"></a>规则说明
 按照约定，标识符名称不包含下划线 (_) 字符。 该规则将检查命名空间、 类型、 成员和参数。

 命名约定提供了通用的外观的库，面向公共语言运行时。 这减少了学习曲线，才能使用新的软件库和客户更有信心库由在开发的托管代码中有专业技能的人员。

## <a name="how-to-fix-violations"></a>如何解决冲突
 从名称中删除所有下划线字符。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="related-rules"></a>相关的规则
 [CA1709：标识符的大小写应当正确](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708：标识符不应仅以大小写进行区分](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)