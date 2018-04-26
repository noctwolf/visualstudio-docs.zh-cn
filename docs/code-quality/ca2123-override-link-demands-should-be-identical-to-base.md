---
title: CA2123：重写的链接请求应与基相同
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 340b0e7deb12d4568a76d4871eabd49641926dcb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123：重写的链接请求应与基相同
|||
|-|-|
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|
|CheckId|CA2123|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或受保护方法的公共类型中重写一个方法或实现一个接口，并且不具有同一[链接需求](/dotnet/framework/misc/link-demands)与该接口或虚方法。

## <a name="rule-description"></a>规则说明
 该规则将一个方法与其基方法（该基方法为另一个类型中的接口或虚方法）相匹配，然后比较两者的链接请求。 如果在方法或基方法具有链接要求和另一个不会报告冲突。

 如果违反了此规则，则恶意调用方只需调用不安全的方法，可以跳过链接要求。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，应用到重写方法或实现相同的链接要求。 如果这是不可能，将标记具有完全的请求的方法或完全删除特性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示各种违反此规则。

 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]

## <a name="see-also"></a>请参阅
 [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)[链接需求](/dotnet/framework/misc/link-demands)