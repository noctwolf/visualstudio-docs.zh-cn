---
title: CA2139：透明方法不能使用 HandleProcessCorruptingExceptions 特性
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2139
ms.assetid: 45a0328a-add7-40f9-8934-dff59beb02b3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f10eca96b9a55d6dfd8d5550bcf7b2d5c08a1a5b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute"></a>CA2139：透明方法不能使用 HandleProcessCorruptingExceptions 特性
|||
|-|-|
|TypeName|TransparentMethodsMustNotHandleProcessCorruptingExceptions|
|CheckId|CA2139|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 透明方法标记为<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>属性。

## <a name="rule-description"></a>规则说明
 将引发此规则是透明的并尝试处理进程损坏异常通过使用任何方法<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>属性。 进程损坏异常属于异常此类的 CLR 版本 4.0 异常分类<xref:System.AccessViolationException>。 HandleProcessCorruptedStateExceptionsAttribute 特性只由安全关键方法使用，并且如果应用于透明的方法，则将被忽略。 若要处理进程损坏异常，此方法必须成为安全关键或安全可靠关键。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，移除<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>特性，或此方法标记<xref:System.Security.SecurityCriticalAttribute>或<xref:System.Security.SecuritySafeCriticalAttribute>属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 在此示例中，透明方法将标有<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>特性并将违反规则。 此外应将方法标记与<xref:System.Security.SecurityCriticalAttribute>或<xref:System.Security.SecuritySafeCriticalAttribute>属性。

 [!code-csharp[FxCop.Security.CA2139.TransparentMethodsMustNotHandleProcessCorruptingExceptions#1](../code-quality/codesnippet/CSharp/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute_1.cs)]