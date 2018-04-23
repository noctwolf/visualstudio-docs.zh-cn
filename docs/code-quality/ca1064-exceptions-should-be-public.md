---
title: CA1064：异常应该是公共的
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 73daa2d834342cf9d4759d569cd637661696e34d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064：异常应该是公共的
|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|类别|Microsoft.Design|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 非公共异常派生直接自<xref:System.Exception>， <xref:System.SystemException>，或<xref:System.ApplicationException>。

## <a name="rule-description"></a>规则说明
 内部异常仅在其自己的内部范围内可见。 当异常超出内部范围后，只能使用基异常来捕获该异常。 如果内部异常继承自<xref:System.Exception>， <xref:System.SystemException>，或<xref:System.ApplicationException>，外部代码将没有足够的信息来了解如何处理异常。

 但是，如果代码有更高版本用作基内部异常的公共异常，那么是合乎情理假定此代码进一步出将能够执行某些智能与使用基异常。 公共异常将包含与所提供的内容的详细信息<xref:System.Exception>， <xref:System.SystemException>，或<xref:System.ApplicationException>。

## <a name="how-to-fix-violations"></a>如何解决冲突
 使该异常公共，或其派生从不是公共异常的内部异常<xref:System.Exception>， <xref:System.SystemException>，或<xref:System.ApplicationException>。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果你确信在所有情况下，将在其自己的内部范围内捕获私有异常，禁止显示此规则的消息。

## <a name="example"></a>示例
 因为异常类直接从异常派生的并且是内部，则将引发此规则在第一个示例方法，FirstCustomException。 因为尽管直接从异常还派生类，类声明为公共规则不会触发 SecondCustomException 类上。 第三个类也不会触发该规则，因为它不是派生直接<xref:System.Exception?displayProperty=fullName>， <xref:System.SystemException?displayProperty=fullName>，或<xref:System.ApplicationException?displayProperty=fullName>。

 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]
