---
title: CA2143:透明方法不应使用安全请求
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 08a7c4d6d7c71954869311b402eed65492391432
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043072"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143:透明方法不应使用安全请求

|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 透明类型或方法将以声明方式标有<xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>`.Demand`方法调用或需<xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>方法。

## <a name="rule-description"></a>规则说明
 安全透明代码不应负责验证某个操作的安全，因此不应要求权限。 安全透明代码应使用完整的需求来作出安全决策并且安全关键代码不应依赖透明代码以进行完全的请求。 执行安全检查，如安全请求，任何代码而是应该是可靠关键。

## <a name="how-to-fix-violations"></a>如何解决冲突
 一般情况下，若要解决此规则的冲突，此方法标记<xref:System.Security.SecuritySafeCriticalAttribute>属性。 此外可以删除该要求。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 规则文件上的以下代码，因为透明方法发出一个声明性安全要求。

 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]

## <a name="see-also"></a>请参阅
 [CA2142:不应使用 Linkdemand 保护透明代码](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)