---
title: CA1046:不要对引用类型重载相等运算符
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c7d3994c827e7d090ead52d0ea6345ba8d79b2a3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018499"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046:不要对引用类型重载相等运算符

|||
|-|-|
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|
|CheckId|CA1046|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或嵌套公共引用类型重载相等运算符。

## <a name="rule-description"></a>规则说明
 对于引用类型，相等运算符的默认实现几乎始终是正确的。 默认情况下，仅当两个引用指向同一对象时，它们才相等。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除相等运算符的实现。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告时引用类型的行为类似于内置值类型。 如果它是类型的有意义，若要执行相加或相减实例，则可能是类型的正确实现相等运算符，并禁止显示冲突。

## <a name="example"></a>示例
 比较两个引用时，下面的示例演示默认行为。

 [!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_1.cs)]

## <a name="example"></a>示例

下面的应用程序将一些引用进行比较。

[!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_2.cs)]

该示例产生下面的输出：

```txt
a = new (2,2) and b = new (2,2) are equal? No
c and a are equal? Yes
b and a are == ? No
c and a are == ? Yes
```

## <a name="related-rules"></a>相关的规则

[CA1013:重载相等运算符，加法和减法](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>请参阅

- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [相等运算符](/dotnet/standard/design-guidelines/equality-operators)