---
title: CA2130:安全关键常量应是透明的
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a33b650570981f5496813f575b1ae2413a960026
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920776"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130:安全关键常量应是透明的

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
常数字段或枚举成员用<xref:System.Security.SecurityCriticalAttribute>进行标记。

## <a name="rule-description"></a>规则说明
未对常数值实施透明强制，因为编译器内联常数值以便在运行时不需要查找。 常数字段应为安全透明的，以便代码评审阅者不会假定透明代码不能访问常数。

## <a name="how-to-fix-violations"></a>如何解决冲突
若要修复与此规则的冲突, 请从字段或值中删除 SecurityCritical 属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
不禁止显示此规则发出的警告。

## <a name="example"></a>示例
在下面的示例中, 枚举值`EnumWithCriticalValues.CriticalEnumValue`和常量`CriticalConstant`引发此警告。 若要解决这些问题, 请删除`SecurityCritical`[] 特性, 使其安全透明。

[!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]