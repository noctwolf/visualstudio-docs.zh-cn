---
title: CA2116：APTCA 方法应只调用 APTCA 方法
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 300b08d6fd00a9bf2a38e738a3b4d433111cb8c7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116：APTCA 方法应只调用 APTCA 方法
|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 中包含的程序集的方法<xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName>特性的程序集中不具有属性的调用的方法。

## <a name="rule-description"></a>规则说明
 默认情况下，具有强名称的程序集的公共或受保护方法隐式受[链接需求](/dotnet/framework/misc/link-demands)完全信任; 只能完全受信任调用方可以访问的强名称程序集。 强名称的程序集标记为<xref:System.Security.AllowPartiallyTrustedCallersAttribute>(APTCA) 特性未启用此保护。 该属性禁用此链接要求，使该程序集不具有完全信任，如执行从 intranet 或 Internet 的代码的调用方可以访问。

 APTCA 特性在完全受信任的程序集后，该程序集执行代码中不允许部分受信任的调用方的另一个程序集，则可能产生安全漏洞。 如果两个方法`M1`和`M2`满足以下条件，则恶意调用方可以使用该方法`M1`绕过的隐式的完全信任链接要求保护`M2`:

-   `M1` 在完全受信任的程序集具有 APTCA 特性中声明的公共方法。

-   `M1` 调用方法`M2`外部`M1`的程序集。

-   `M2`程序集不具有 APTCA 特性，并且，因此，不应执行的操作或代表部分受信任的调用方。

 部分受信任的调用方`X`可以调用方法`M1`，从而导致`M1`调用`M2`。 因为`M2`没有 APTCA 特性，其直接调用方 (`M1`) 必须满足针对完全信任; 的链接要求`M1`具有完全信任权限并且因此满足此检查。 安全风险是因为`X`不参与满足此链接要求保护`M2`通过不受信任的调用方。 因此，用 APTCA 特性方法不得调用不具有属性的方法。

## <a name="how-to-fix-violations"></a>如何解决冲突
 如果 APCTA 特性是必需的则使用要求来保护调入完全信任程序集的方法。 确切的权限，您需将取决于你的方法所公开的功能。 如果可能，保护要求完全信任以确保基础功能不会公开给部分受信任的调用方提供的方法。 如果这是不可能，请选择有效地保护已公开的功能的权限集。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 若要安全地禁止显示此规则的警告，必须确保由你的方法公开的功能不会直接或间接允许调用方访问敏感信息、 操作或可以以的破坏性方式使用的资源。

## <a name="example"></a>示例
 下面的示例使用两个程序集和测试应用程序演示此规则检测到的安全漏洞。 第一个程序集不具有 APTCA 特性和不应为供部分受信任的调用方 (由表示`M2`前面讨论)。

 [!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]

## <a name="example"></a>示例
 第二个程序集是完全受信任，允许部分受信任的调用方 (由表示`M1`前面讨论)。

 [!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]

## <a name="example"></a>示例
 测试应用程序 (由表示`X`前面讨论中) 是部分受信任。

 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]

 本示例生成以下输出。

 **要求完全信任： 请求失败。** 
 **ClassRequiringFullTrust.DoWork 调用。**
## <a name="related-rules"></a>相关的规则
 [CA2117：APTCA 类型应只扩展 APTCA 基类型](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>请参阅
 [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)[通过使用库部分受信任的代码](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)[链接需求](/dotnet/framework/misc/link-demands)[数据和建模](/dotnet/framework/data/index)