---
title: CA2135： 级别 2 程序集不应包含 Linkdemand |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 9df472598587e90ad56ecc77a1d58c4094b2e61c
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "47588950"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135：级别 2 程序集不应包含 LinkDemand
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA2135： 级别 2 程序集不应包含 Linkdemand](https://docs.microsoft.com/visualstudio/code-quality/ca2135-level-2-assemblies-should-not-contain-linkdemands)。

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

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2135.securityrulesetlevel2methodsshouldnotbeprotectedwithlinkdemands/cs/ca2135.cs#1)]



