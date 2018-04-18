---
title: CA2133： 委托必须绑定到方法具有一致透明度 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ff3811803e65028e44790dfecac9098168f53f7b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133：委托必须绑定到具有一致透明度的方法
|||  
|-|-|  
|TypeName|DelegatesMustBindWithConsistentTransparency|  
|CheckId|CA2133|  
|类别|Microsoft.Security|  
|是否重大更改|重大|  
  
> [!NOTE]
>  此警告仅应用于运行 CoreCLR （特定于 Silverlight 的 Web 应用程序的 clr 的版本） 的代码。  
  
## <a name="cause"></a>原因  
 对用标记的委托绑定的方法引发此警告<xref:System.Security.SecurityCriticalAttribute>透明的或用标记的方法<xref:System.Security.SecuritySafeCriticalAttribute>。 还会对另一个具有以下特点的方法引发此警告：该方法将透明的或安全关键的委托绑定到一个关键方法。  
  
## <a name="rule-description"></a>规则说明  
 委托类型和其绑定到的方法必须具有一致的透明度。 透明和安全关键的委托可能只能绑定到其他透明或安全关键方法。 同样，关键的委托可能仅绑定到关键方法。 这些绑定规则确保可以在调用委托通过方法的唯一代码无法具有还调用同一方法直接。 例如，绑定规则阻止透明代码调用关键代码直接通过透明的委托。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 若要修复与此警告的冲突，更改该委托的或它绑定，以便这两个透明度是等效的方法的透明度。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 不禁止显示此规则发出的警告。  
  
### <a name="code"></a>代码  
 [!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2133-delegates-must-bind-to-methods-with-consistent-transparency_1.cs)]