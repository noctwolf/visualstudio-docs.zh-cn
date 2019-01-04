---
title: CA2133:委托必须绑定到具有一致透明度的方法
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8053090802c77b310bc04d6e95be8d3c538a4cb9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53939779"
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133:委托必须绑定到具有一致透明度的方法

|||
|-|-|
|TypeName|DelegatesMustBindWithConsistentTransparency|
|CheckId|CA2133|
|类别|Microsoft.Security|
|是否重大更改|重大|

> [!NOTE]
> 此警告仅应用于运行 CoreCLR （Silverlight web 应用程序特定的 CLR 的版本） 的代码。

## <a name="cause"></a>原因

引发此警告： 上的方法的委托绑定将标有<xref:System.Security.SecurityCriticalAttribute>的方法是透明的或标记的<xref:System.Security.SecuritySafeCriticalAttribute>。 还会对另一个具有以下特点的方法引发此警告：该方法将透明的或安全关键的委托绑定到一个关键方法。

## <a name="rule-description"></a>规则说明

委托类型以及它们绑定到的方法必须具有一致的透明度。 透明且可靠关键的委托可能仅绑定到其他透明或安全关键方法。 同样，关键的委托可能仅绑定到关键方法。 这些绑定规则可确保，可以调用的方法通过委托的唯一代码可能有也相同的方法直接调用。 例如，绑定规则阻止透明代码调用关键代码直接通过透明委托。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此警告的冲突，请更改透明度或此属性绑定，以便两个透明度是等效的方法的委托。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。

### <a name="code"></a>代码

[!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2133-delegates-must-bind-to-methods-with-consistent-transparency_1.cs)]