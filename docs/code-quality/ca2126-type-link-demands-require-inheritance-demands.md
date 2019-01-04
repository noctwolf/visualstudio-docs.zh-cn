---
title: CA2126:类型链接请求需要继承请求
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 834f120994070e055fe5ac417d1fb39830c7bcef
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53904135"
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126:类型链接请求需要继承请求

|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 一个公共的非密封的类型受保护的链接要求，具有可重写的方法，并且类型和方法都不受继承要求保护。

## <a name="rule-description"></a>规则说明
 对方法或其声明类型链接请求要求直接调用方的方法具有指定的权限。 在方法上的继承请求要求重写方法，以使指定的权限。 对一种类型的继承请求要求派生类具有指定的权限。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，安全的类型或方法替换为链接要求相同的权限继承要求。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例显示了违反了此规则的类型。

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA2108:检查有关值类型的声明性安全](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA2112:受保护的类型不应公开字段](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA2122:不要间接公开方法使用链接请求](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123:重写链接请求应与基相同](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>请参阅

- [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)
- [链接需求](/dotnet/framework/misc/link-demands)