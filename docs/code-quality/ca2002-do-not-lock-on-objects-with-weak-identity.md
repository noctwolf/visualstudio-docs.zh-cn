---
title: CA2002：不要锁定具有弱标识的对象
ms.date: 01/31/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotLockOnObjectsWithWeakIdentity
- CA2002
helpviewer_keywords:
- CA2002
- DoNotLockOnObjectsWithWeakIdentity
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7708f5e968fed8765ca27bff99d479957927440b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2002-do-not-lock-on-objects-with-weak-identity"></a>CA2002：不要锁定具有弱标识的对象

|||
|-|-|
|TypeName|DoNotLockOnObjectsWithWeakIdentity|
|CheckId|CA2002|
|类别|Microsoft.Reliability|
|是否重大更改|非重大|

## <a name="cause"></a>原因

线程尝试获取对具有弱标识的对象的锁。

## <a name="rule-description"></a>规则说明

当可以跨应用程序域边界直接进行访问对象时，则认为该对象具有弱标识。 对于尝试获取对具有弱标识的对象的锁的线程，该线程可能会被其他应用程序域中持有对同一对象的锁的另一线程所阻止。

以下类型具有弱标识，并会将标记规则：

- <xref:System.String>

- 值类型，包括数组[整型](/dotnet/csharp/language-reference/keywords/integral-types-table)，[浮点类型](/dotnet/csharp/language-reference/keywords/floating-point-types-table)，和<xref:System.Boolean>。

- <xref:System.MarshalByRefObject>

- <xref:System.ExecutionEngineException>

- <xref:System.OutOfMemoryException>

- <xref:System.StackOverflowException>

- <xref:System.Reflection.MemberInfo>

- <xref:System.Reflection.ParameterInfo>

- <xref:System.Threading.Thread>

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复与此规则的冲突，使用不在描述部分的列表中的类型中的对象。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。

## <a name="related-rules"></a>相关的规则

[CA2213：应释放可释放的字段](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

## <a name="example"></a>示例

下面的示例演示某些违反规则的对象锁。

[!code-vb[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/VisualBasic/ca2002-do-not-lock-on-objects-with-weak-identity_1.vb)]
[!code-csharp[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/CSharp/ca2002-do-not-lock-on-objects-with-weak-identity_1.cs)]

## <a name="see-also"></a>请参阅

<xref:System.Threading.Monitor>
<xref:System.AppDomain>
[锁定语句 (C#)](/dotnet/csharp/language-reference/keywords/lock-statement)
[SyncLock 语句 (Visual Basic)](/dotnet/visual-basic/language-reference/statements/synclock-statement)