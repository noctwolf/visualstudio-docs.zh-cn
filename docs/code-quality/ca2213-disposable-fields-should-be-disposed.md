---
title: CA2213：应释放可释放的字段
ms.date: 11/05/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be06c9bf38ec360cedc858d92a84b1f89c662856
ms.sourcegitcommit: bccb05b5b4e435f3c1f7c36ba342e7d4031eb398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "51220627"
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213：应释放可释放的字段

|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

实现的类型<xref:System.IDisposable?displayProperty=fullName>声明还实现的类型的字段<xref:System.IDisposable>。 <xref:System.IDisposable.Dispose%2A>字段的方法不由调用<xref:System.IDisposable.Dispose%2A>声明类型的方法。

## <a name="rule-description"></a>规则说明

一种类型负责释放其所有非托管资源。 规则 CA2213 检查以查看是否可释放类型 (即，一个实现<xref:System.IDisposable>)`T`声明字段`F`，它是可释放类型的实例`FT`。 每个字段`F`的已分配给本地创建的对象方法或包含类型的初始值设定项内`T`，规则将尝试查找调用`FT.Dispose`。 该规则会搜索调用的方法`T.Dispose`和一个级别较低 (即，调用的方法调用的方法`FT.Dispose`)。

> [!NOTE]
> CA2213 激发仅用于分配包含类型的方法和初始值设定项中的本地创建可释放对象的字段的规则。 如果创建或分配外部类型的对象`T`，该规则不会激发。 这将减少干扰的情况下，其中包含类型本身不必拥有负责释放的对象。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请调用<xref:System.IDisposable.Dispose%2A>所实现的类型的字段上<xref:System.IDisposable>。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

则可以安全地禁止显示此规则的警告，如果您不负责为释放资源持有的字段，或如果调用<xref:System.IDisposable.Dispose%2A>在更深层次的调用规则检查级别上发生。

## <a name="example"></a>示例

以下代码片段显示了一种类型`TypeA`实现<xref:System.IDisposable>。

[!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

以下代码片段显示了一种类型`TypeB`，通过声明一个字段违反规则 CA2213`aFieldOfADisposableType`作为可释放类型 (`TypeA`) 而不调用<xref:System.IDisposable.Dispose%2A>字段上。

[!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

## <a name="see-also"></a>请参阅

- <xref:System.IDisposable?displayProperty=fullName>
- [释放模式](/dotnet/standard/design-guidelines/dispose-pattern)