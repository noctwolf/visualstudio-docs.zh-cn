---
title: CA2226:运算符应有对称重载
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
helpviewer_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c6a38f6f4e76f5195e042b0ede2b2a8a5384a1cf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54938011"
---
# <a name="ca2226-operators-should-have-symmetrical-overloads"></a>CA2226:运算符应有对称重载

|||
|-|-|
|TypeName|OperatorsShouldHaveSymmetricalOverloads|
|CheckId|CA2226|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 某个类型实现了相等运算符或不等运算符，却未实现相反运算符。

## <a name="rule-description"></a>规则说明
 有任何情况下，其中等式或不等式是适用于某种类型的实例，未定义相反运算符。 类型通常通过返回的相反的值的相等运算符实现不等运算符。

 C# 编译器会发出有关此规则冲突错误。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，可实现相等和不相等运算符或删除的存在。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 你的类型不会与.NET Framework 是一致的方式。

## <a name="related-rules"></a>相关的规则
 [CA1046:请重载相等运算符对引用类型](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225:运算符重载具有命名的备用项](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2224:重写 equals 方法重载相等运算符](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218:重写 Equals 时重写 GetHashCode](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231：重写 ValueType.Equals 时应重载相等运算符](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)