---
title: CA2141：透明方法不得满足 LinkDemand
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 59b8c01f6e542093268c31d1edaf29d690aa6c5e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54926497"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141：透明方法不得满足 LinkDemand

|||
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 安全透明方法调用中未标有程序集的方法<xref:System.Security.AllowPartiallyTrustedCallersAttribute>(APTCA) 特性或一个安全透明方法满足<xref:System.Security.Permissions.SecurityAction>`.LinkDemand`类型或方法。

## <a name="rule-description"></a>规则说明
 满足 LinkDemand 是安全敏感操作，可能会导致无意提升权限。 安全透明代码不得满足 Linkdemand，因为它不遵循相同的安全审核要求与安全关键代码。 在安全规则集第 1 级程序集中的透明方法将导致所有 linkdemands 都将它们满足要转换为完整的需求，在运行时，可能会导致性能问题。 安全规则集级别 2 程序集，将无法编译在实时 (JIT) 编译器中，如果用户尝试满足 LinkDemand 透明方法。

 在使用 2 级安全的程序集中，尝试通过安全透明方法满足 LinkDemand 或调用非 APTCA 程序集中的一种方法将引发<xref:System.MethodAccessException>; 在第 1 级程序集中 LinkDemand 变成完全要求。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请将标记具有的访问方法<xref:System.Security.SecurityCriticalAttribute>或<xref:System.Security.SecuritySafeCriticalAttribute>特性，或从访问方法移除 LinkDemand。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 在此示例中，透明方法尝试调用具有 LinkDemand 的方法。 此规则将触发对此代码。

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../code-quality/codesnippet/CSharp/ca2141-transparent-methods-must-not-satisfy-linkdemands_1.cs)]