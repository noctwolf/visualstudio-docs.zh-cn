---
title: CA2116:APTCA 方法应只调用 APTCA 方法
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6ecd6c5a51feb025eb5e90fa63ae0b2a8bf877ed
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029786"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116:APTCA 方法应只调用 APTCA 方法

|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因

方法的程序集中<xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName>属性调用中不具有属性的程序集的方法。

## <a name="rule-description"></a>规则说明

默认情况下，具有强名称的程序集的公共或受保护方法隐式受[链接要求](/dotnet/framework/misc/link-demands)的完全信任; 只有完全受信任调用方可以访问的强名称程序集。 用强名称的程序集标记<xref:System.Security.AllowPartiallyTrustedCallersAttribute>(APTCA) 特性不具有这种保护。 该属性禁用链接要求，使该程序集未获得完全信任，如从 intranet 或 Internet 中执行的代码的调用方访问。

APTCA 属性为完全受信任的程序集，并且该程序集执行代码中不允许部分受信任调用方的另一个程序集，则可能会产生安全问题。 如果两个方法`M1`并`M2`满足以下条件，则恶意调用方可以使用该方法`M1`绕过的完全信任隐式链接要求保护`M2`:

- `M1` 在完全受信任的程序集具有 APTCA 特性中声明的公共方法。

- `M1` 调用的方法`M2`外部`M1`的程序集。

- `M2`程序集不具有 APTCA 特性，并且，因此，不应执行或代表部分受信任的调用方。

部分受信任调用方`X`可以调用方法`M1`，从而导致`M1`调用`M2`。 因为`M2`不具有 APTCA 属性，其直接调用方 (`M1`) 必须满足链接请求完全信任;`M1`具有完全信任权限，因此满足此检查。 安全风险是因为`X`不参与满足保护的链接要求`M2`通过不受信任的调用方。 因此，具有 APTCA 特性的方法必须调用没有该属性的方法。

## <a name="how-to-fix-violations"></a>如何解决冲突
 APCTA 特性是必需的如果使用要求来保护到完全信任程序集调用的方法。 将取决于您需求的确切权限方法公开的功能。 如果可能，保护要求完全信任，以确保不向部分受信任调用方公开的基本功能的方法。 如果这不可能，请选择有效地保护提供的功能的一组权限。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 若要安全地禁止显示此规则的警告，必须确保由你的方法公开的功能不直接或间接允许调用方访问敏感信息、 操作或可以以破坏方式使用的资源。

## <a name="example-1"></a>示例 1
 以下示例使用两个程序集和测试应用程序来演示此规则检测到的安全漏洞。 第一个程序集没有 APTCA 特性，并且不应访问的部分受信任调用方 (由`M2`前面讨论)。

 [!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]

## <a name="example-2"></a>示例 2
 第二个程序集是完全受信任，允许部分受信任调用方 (由`M1`前面讨论)。

 [!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]

## <a name="example-3"></a>示例 3
 测试应用程序 (由`X`前面讨论) 是部分受信任。

 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]

该示例产生下面的输出：

```txt
Demand for full trust:Request failed.
ClassRequiringFullTrust.DoWork was called.
```

## <a name="related-rules"></a>相关的规则

- [CA2117:APTCA 类型应只扩展 APTCA 基类型](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>请参阅

- [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)
- [通过部分受信任的代码使用库](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)
- [链接需求](/dotnet/framework/misc/link-demands)
- [数据和建模](/dotnet/framework/data/index)