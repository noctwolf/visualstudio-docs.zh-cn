---
title: CA2135:级别 2 程序集不应包含 LinkDemand
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 61f41a47b7fbb27e1811bd2c9888baf01143a50f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53904096"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135:级别 2 程序集不应包含 LinkDemand

|||
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 使用类或类成员<xref:System.Security.Permissions.SecurityAction>使用 2 级安全的应用程序中。

## <a name="rule-description"></a>规则说明
 在级别为 2 的安全规则集中已弃用 LinkDemand。 而不是使用 Linkdemand 在实时 (JIT) 编译时强制安全，将标记方法、 类型和字段与<xref:System.Security.SecurityCriticalAttribute>属性。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除<xref:System.Security.Permissions.SecurityAction>和标记的类型或成员<xref:System.Security.SecurityCriticalAttribute>属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 在以下示例中，<xref:System.Security.Permissions.SecurityAction>应被删除，该方法标记有<xref:System.Security.SecurityCriticalAttribute>属性。

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2135-level-2-assemblies-should-not-contain-linkdemands_1.cs)]