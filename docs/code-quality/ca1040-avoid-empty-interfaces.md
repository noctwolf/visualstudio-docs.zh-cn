---
title: CA1040：避免使用空接口
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 247344cac2f2f36d1db28d1fe217cbfa5d9b6234
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040：避免使用空接口
|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 接口不声明任何成员，也不实现两个或多个其他接口。

## <a name="rule-description"></a>规则说明
 接口定义提供某个行为或使用协定的成员。 接口所描述的功能可以被任何类型采用，而不管该类型出现在继承层次结构中的哪个位置。 类型通过实现接口的成员来实现接口。 空接口无法定义任何成员。 因此，它无法定义可以实现的协定。

 如果你的设计包括空类型的接口预计将实现，可以将接口作为标记或者标识的一组类型一种方式使用。 如果在运行时，会出现此标识，实现此目的的正确方法是使用自定义属性。 使用的状态或不存在该属性或该属性的属性以确定目标类型。 如果该标识必须出现在编译时，它是可接受使用空接口。

## <a name="how-to-fix-violations"></a>如何解决冲突
 移除该接口或向其添加成员。 如果空接口用于标记一组类型，将替换的自定义特性的接口。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 则可以安全地禁止显示此规则的警告，该接口用于编译时标识的一组类型时。

## <a name="example"></a>示例
 下面的示例演示一个空的接口。

 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]