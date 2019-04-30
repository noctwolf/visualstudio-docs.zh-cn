---
title: CA2123:重写链接请求应与基相同
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 52959279bca5aa0f86722050f6118f64997a901d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545040"
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123:重写链接请求应与基相同

|||
|-|-|
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|
|CheckId|CA2123|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或受保护方法的公共类型中重写的方法或实现一个接口，并且不具有相同[链接要求](/dotnet/framework/misc/link-demands)作为接口或虚方法。

## <a name="rule-description"></a>规则说明
 该规则将一个方法与其基方法（该基方法为另一个类型中的接口或虚方法）相匹配，然后比较两者的链接请求。 如果在方法或基方法具有链接要求，并且另一个不会报告冲突。

 如果违反此规则，则恶意调用方只是调用不安全的方法，可以跳过链接要求。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请重写方法或实现应用相同的链接要求。 如果无法做到这一点，此方法的完全要求标记或完全删除该属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示各种违反此规则。

 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]

## <a name="see-also"></a>请参阅

- [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)
- [链接需求](/dotnet/framework/misc/link-demands)