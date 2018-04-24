---
title: CA2126：类型链接请求需要继承请求
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a9ee3817d445144c3c83756cda07da2ed41adee6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126：类型链接请求需要继承请求
|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 一个公共的非密封的类型受链接要求，具有可重写的方法，与类型和方法都不受继承要求保护。

## <a name="rule-description"></a>规则说明
 链接要求对方法或其声明类型要求立即方法的调用方拥有指定的权限。 继承要求的方法上需要的重写一个方法具有指定的权限。 对一种类型的继承请求要求派生类必须具有指定的权限。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，保护类型或具有一个针对作为此链接要求相同的权限继承要求的方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示与该规则冲突的类型。

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA2108：检查有关值类型的声明性安全](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA2112：受保护的类型不应公开字段](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA2122：不要使用链接请求间接公开方法](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123：重写的链接请求应与基相同](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>请参阅
 [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)[链接需求](/dotnet/framework/misc/link-demands)
