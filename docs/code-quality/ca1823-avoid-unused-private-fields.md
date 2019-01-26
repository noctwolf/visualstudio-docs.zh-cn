---
title: CA1823:避免未使用的私有字段
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AvoidUnusedPrivateFields
- CA1823
helpviewer_keywords:
- AvoidUnusedPrivateFields
- CA1823
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ad70fbcb8052e45f4819db2f8d423ce4f70ce697
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971528"
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823:避免未使用的私有字段

|||
|-|-|
|TypeName|AvoidUnusedPrivateFields|
|CheckId|CA1823|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 在代码中的私有字段存在，但不是由任何代码路径时，会报告此规则。

## <a name="rule-description"></a>规则说明
 检测到程序集内有似乎未访问过的私有字段。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除字段或添加使用它的代码。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告。

## <a name="related-rules"></a>相关的规则
 [CA1812:避免未实例化的内部类](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801:检查未使用的参数](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804:删除未使用的局部变量](../code-quality/ca1804-remove-unused-locals.md)

 [CA1811:避免使用未调用的私有代码](../code-quality/ca1811-avoid-uncalled-private-code.md)