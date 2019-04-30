---
title: CA1033:接口方法应可由子类型调用
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1fd8ee08b53ef3f9216edcb67ebcdbe6c4978bb3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778839"
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033:接口方法应可由子类型调用

|||
|-|-|
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|
|CheckId|CA1033|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 未密封的外部可见类型提供了显式实现公共接口的方法，但没有提供具有相同名称的其他外部可见方法。

## <a name="rule-description"></a>规则说明
 请考虑显式实现公共接口方法的基类型。 基类型派生的类型可以仅通过对当前实例的引用访问继承的接口方法 (`this` C# 中)，其强制转换到的接口。 如果派生的类型 （显式） 重新实现继承的接口方法，不再可以访问的基实现。 通过当前实例引用的调用将调用派生的实现;这将导致递归和最终堆栈溢出。

 此规则不会报告的显式实现的冲突<xref:System.IDisposable.Dispose%2A?displayProperty=fullName>时外部可见`Close()`或`System.IDisposable.Dispose(Boolean)`提供方法。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，实现新方法，用于公开相同的功能并对派生类型可见，或将更改为非显式实现。 如果一项重大更改是可接受的一种替代方法是密封的类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告，如果外部可见方法提供了具有相同的功能，但不同于显式实现的方法的名称。

## <a name="example"></a>示例
 下面的示例演示一种类型， `ViolatingBase`，这违反了规则和一个类型， `FixedBase`，显示冲突的修复程序。

 [!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../code-quality/codesnippet/CSharp/ca1033-interface-methods-should-be-callable-by-child-types_1.cs)]

## <a name="see-also"></a>请参阅
 [接口](/dotnet/csharp/programming-guide/interfaces/index)