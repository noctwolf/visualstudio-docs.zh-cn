---
title: CA1504：检查令人误解的字段名
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0caf5e8c158f2c434bd20e4b033ed1e2f7f37e5f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504：检查令人误解的字段名
|||
|-|-|
|TypeName|ReviewMisleadingFieldNames|
|CheckId|CA1504|
|类别|Microsoft.Maintainability|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 实例字段的名称以"s_"或名称开头`static`(`Shared`中[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 以"m_"开头的字段。

## <a name="rule-description"></a>规则说明
 以"s_"开头的字段名是由多个用户的静态数据相关联。 同样，以"m_"开头的字段名是与实例 （成员） 的数据关联。 对于更易于维护的代码，名称应遵循通常使用的约定。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，请使用相应的前缀重命名字段。 另外，还可以使该字段与当前后缀相符通过添加或删除`static`修饰符。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。