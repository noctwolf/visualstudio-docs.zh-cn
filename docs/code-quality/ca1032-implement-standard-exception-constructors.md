---
title: CA1032:实现标准异常构造函数
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1032
- ImplementStandardExceptionConstructors
helpviewer_keywords:
- CA1032
- ImplementStandardExceptionConstructors
ms.assetid: a8623c56-273a-4c95-8d83-95911a042be7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 947b22929c58ce962861c65946941513d7845152
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957776"
---
# <a name="ca1032-implement-standard-exception-constructors"></a>CA1032:实现标准异常构造函数

|||
|-|-|
|TypeName|ImplementStandardExceptionConstructors|
|CheckId|CA1032|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因

类型扩展<xref:System.Exception?displayProperty=fullName>但不声明所需的所有构造函数。

## <a name="rule-description"></a>规则说明

异常类型必须实现以下三个构造函数：

- public NewException()

- public NewException(string)

- public NewException(string, Exception)

此外，如果运行的旧的 FxCop 静态代码分析作为而不是[基于 Roslyn 的 FxCop 分析器](../code-quality/roslyn-analyzers-overview.md)，缺少第四个构造函数还会生成与冲突：

- 受保护或私有 NewException （SerializationInfo，StreamingContext）

如果不能提供完整的构造函数集，要正确处理异常将变得比较困难。 例如，已签名的构造函数`NewException(string, Exception)`用于创建的其他异常导致的异常。 没有此构造函数，不能创建和引发自定义异常，其中包含内部 （嵌套） 异常，这是在这种情况下应执行哪些托管的代码的实例。

前三种异常构造函数是公共的约定。 第四个构造函数是在未密封类中，受保护和私钥在密封类中。 有关详细信息，请参阅[CA2229:实现序列化构造函数](../code-quality/ca2229-implement-serialization-constructors.md)

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请将缺少的构造函数添加到异常，并确保它们具有正确的可访问性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

它可以安全地禁止显示此规则的警告时冲突导致的公共构造函数使用不同的访问级别。 此外，它是可以取消警告`NewException(SerializationInfo, StreamingContext)`构造函数，如果您正在构建可移植类库 (PCL)。

## <a name="example"></a>示例

下面的示例包含与此规则冲突的异常类型和一个正确实现的异常类型。

[!code-csharp[FxCop.Design.ExceptionMultipleCtors#1](../code-quality/codesnippet/CSharp/ca1032-implement-standard-exception-constructors_1.cs)]

## <a name="see-also"></a>请参阅

[CA2229：实现序列化构造函数](../code-quality/ca2229-implement-serialization-constructors.md)