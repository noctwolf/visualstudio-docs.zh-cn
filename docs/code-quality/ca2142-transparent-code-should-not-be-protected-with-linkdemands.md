---
title: CA2142： 透明代码应不使用 Linkdemand 保护 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c598a6aff671f0ce3ce489a203805e77eda7183
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142：不应使用 LinkDemand 保护透明代码
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|  
|CheckId|CA2142|  
|类别|Microsoft.Security|  
|是否重大更改|重大|  
  
## <a name="cause"></a>原因  
 透明方法需要<xref:System.Security.Permissions.SecurityAction>或其他安全要求。  
  
## <a name="rule-description"></a>规则说明  
 对于需要 LinkDemand 来访问它们的透明方法，将会引发此规则。 安全透明代码不应负责验证某个操作的安全，因此不应要求权限。 透明方法不会为非特定的安全，因为它们不应作出任何安全决策。 此外，安全关键代码，未作出安全决策，不应依赖透明代码以之前进行此类决策。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 若要修复与此规则的冲突，删除此链接要求的透明方法，或此方法标记<xref:System.Security.SecuritySafeCriticalAttribute>属性，前提它执行安全检查，例如安全要求。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 不禁止显示此规则发出的警告。  
  
## <a name="example"></a>示例  
 因为该方法是透明的则会用 LinkDemand 标记规则的方法引发在以下示例中，<xref:System.Security.PermissionSet>包含<xref:System.Security.Permissions.SecurityAction>。  
  
 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]  
  
 不禁止显示此规则发出的警告。