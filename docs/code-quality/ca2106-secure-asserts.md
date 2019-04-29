---
title: CA2106:保护断言
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c8d80c4e9a21c29ce7b34a3998e241b11713f355
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545695"
---
# <a name="ca2106-secure-asserts"></a>CA2106:保护断言

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 一种方法断言权限，并不执行调用方的任何安全检查。

## <a name="rule-description"></a>规则说明
 如果在不执行任何安全检查的情况下断言安全权限，则会在代码中留下可利用的安全漏洞。 安全堆栈审核停止时断言安全权限。 如果在调用方执行任何检查的情况下断言权限，调用方可以通过使用你的权限间接执行代码。 断言没有安全检查是允许当您确定无法以有害方式使用断言。 声明是无害的如果您调用的代码是无害的或者用户不能将任意信息传递给调用的代码。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请添加对方法或其声明类型安全要求。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 禁止显示此规则在仔细检查安全性后，才的警告。

## <a name="see-also"></a>请参阅

- <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>
- [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)