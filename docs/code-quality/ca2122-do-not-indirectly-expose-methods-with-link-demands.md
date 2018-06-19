---
title: CA2122：不要使用链接请求间接公开方法
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2122
- DoNotIndirectlyExposeMethodsWithLinkDemands
helpviewer_keywords:
- DoNotIndirectlyExposeMethodsWithLinkDemands
- CA2122
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c43cfc1a448d9073a8bbe493d75c7c117f57d737
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915551"
---
# <a name="ca2122-do-not-indirectly-expose-methods-with-link-demands"></a>CA2122：不要使用链接请求间接公开方法
|||
|-|-|
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|
|CheckId|CA2122|
|类别|Microsoft.Security|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 公共或受保护成员具有[链接需求](/dotnet/framework/misc/link-demands)并由不执行任何安全检查的成员调用。

## <a name="rule-description"></a>规则说明
 链接请求仅检查直接调用方的权限。 如果成员`X`发出安全请求其调用方，并在结尾调用代码受链接要求，调用方没有所需的权限可以使用`X`来访问受保护的成员。

## <a name="how-to-fix-violations"></a>如何解决冲突
 添加安全[数据和建模](/dotnet/framework/data/index)或将需求链接到成员，以便它不再提供对受链接要求保护的成员的不安全的访问。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 若要安全地禁止显示此规则的警告，你必须确保你的代码不授予其调用方对操作或可以以的破坏性方式使用的资源的访问。

## <a name="example"></a>示例
 下面的示例演示违反了规则，一个库和应用程序演示库的漏洞。 示例库提供一起违反规则的两种方法。 `EnvironmentSetting`方法受对环境变量的不受限制访问链接要求保护。 `DomainInformation`方法发出其调用方的安全请求，然后才能调用`EnvironmentSetting`。

 [!code-csharp[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]

## <a name="example"></a>示例
 下面的应用程序调用的不安全的库成员。

 [!code-csharp[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]

 本示例生成以下输出。

 **来自不安全的成员的值： seattle.corp.contoso.com**
## <a name="see-also"></a>请参阅
 [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)[链接需求](/dotnet/framework/misc/link-demands)[数据和建模](/dotnet/framework/data/index)