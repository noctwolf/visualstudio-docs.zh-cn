---
title: CA2114:方法安全性应是类型安全性的超集
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d83da42a029d746899bfaccf5d62f8856a040611
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921106"
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114:方法安全性应是类型安全性的超集

|||
|-|-|
|TypeName|MethodSecurityShouldBeASupersetOfType|
|CheckId|CA2114|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
类型具有声明性安全, 其中一种方法为同一安全操作提供声明性安全, 并且安全操作不是[链接要求](/dotnet/framework/misc/link-demands), 且由该类型检查的权限不是方法所检查的权限的子集。

## <a name="rule-description"></a>规则说明
一个方法不应同时具有相同操作的方法级别和类型级别的声明性安全。 这两个检查不组合在一起;仅应用方法级需求。 例如, 如果某一类型要求权限`X`, 并且它的某个方法要求权限`Y`, 则代码不需要具有执行方法`X`的权限。

## <a name="how-to-fix-violations"></a>如何解决冲突
检查代码以确保这两个操作都是必需的。 如果这两个操作都是必需的, 请确保方法级别的操作包括在类型级别指定的安全性。 例如, 如果你的类型需要权限`X`, 并且其方法还必须需要权限`Y`, 则该方法应显式`X`需要`Y`和。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
如果方法不需要类型指定的安全性, 则可以安全地禁止显示此规则发出的警告。 但这并不是一个普通方案, 可能表明需要仔细设计评审。

## <a name="example-1"></a>示例 1

下面的示例使用环境权限来演示违反此规则的危险。 在此示例中, 应用程序代码在拒绝类型所需的权限之前创建了受保护类型的实例。 在实际威胁方案中, 应用程序需要另一种方法来获取对象的实例。

在下面的示例中, 库请求类型的写入权限和对方法的读取权限。

[!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]

## <a name="example-2"></a>示例 2

以下应用程序代码通过调用方法来演示库的漏洞, 即使它不符合类型级安全要求。

[!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]

该示例产生下面的输出：

```txt
[All permissions] Personal information: 6/16/1964 12:00:00 AM
[No write permission (demanded by type)] Personal information: 6/16/1964 12:00:00 AM
[No read permission (demanded by method)] Could not access personal information: Request failed.
```

## <a name="see-also"></a>请参阅

- [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)
- [链接需求](/dotnet/framework/misc/link-demands)
- [数据和建模](/dotnet/framework/data/index)