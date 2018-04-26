---
title: CA2143：透明方法不应使用安全要求
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e6e4bad795ccf89b36d4fc6a12b29ba4ada7fbb9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143：透明方法不应使用安全要求
|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 透明类型或方法以声明方式标记有<xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>`.Demand`需或方法调用<xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>方法。

## <a name="rule-description"></a>规则说明
 安全透明代码不应负责验证某个操作的安全，因此不应要求权限。 安全透明代码应使用完整的需求来作出安全决策并且安全关键代码不应依赖透明代码以进行完全的请求。 执行安全检查，如安全请求，任何代码改为应为安全关键。

## <a name="how-to-fix-violations"></a>如何解决冲突
 一般情况下，若要修复与此规则的冲突，此方法标记<xref:System.Security.SecuritySafeCriticalAttribute>属性。 你还可以删除此要求。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 在下面的代码上的规则文件，因为透明的方法发出的声明性安全要求。

 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]

## <a name="see-also"></a>请参阅
 [CA2142：不应使用 LinkDemand 保护透明代码](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)