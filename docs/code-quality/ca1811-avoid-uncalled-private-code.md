---
title: CA1811:避免使用未调用的私有代码
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AvoidUncalledPrivateCode
- CA1811
helpviewer_keywords:
- CA1811
- AvoidUncalledPrivateCode
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6fca30671616dbe1e9d1c3468420d4526aa02250
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54975148"
---
# <a name="ca1811-avoid-uncalled-private-code"></a>CA1811:避免使用未调用的私有代码

|||
|-|-|
|TypeName|AvoidUncalledPrivateCode|
|CheckId|CA1811|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 私有或内部 （程序集级别） 成员在程序集中没有调用方、 由公共语言运行时，不调用和不由委托调用。 此规则不检查下列成员：

- 显式接口成员。

- 静态构造函数。

- 序列化构造函数。

- 使用标记方法<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName>或<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>。

- 是重写的成员。

## <a name="rule-description"></a>规则说明
 此规则会报告误报入口点会发生，如果当前未标识由规则逻辑。 此外，编译器可能将不可调用的代码发出到程序集。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，删除不可调用的代码或添加调用它的代码。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告。

## <a name="related-rules"></a>相关的规则
 [CA1812:避免未实例化的内部类](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801:检查未使用的参数](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804:删除未使用的局部变量](../code-quality/ca1804-remove-unused-locals.md)