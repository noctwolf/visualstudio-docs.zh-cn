---
title: CA2112:受保护的类型不应公开字段
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2d46c9fe1b97b5bdfb081150a44aa69363eced53
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55922792"
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112:受保护的类型不应公开字段

|||
|-|-|
|TypeName|SecuredTypesShouldNotExposeFields|
|CheckId|CA2112|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或受保护类型包含公共字段，并受[链接要求](/dotnet/framework/misc/link-demands)。

## <a name="rule-description"></a>规则说明
 如果代码可以访问受链接要求保护的类型的实例，则该代码不必满足此链接要求就可以访问该类型的字段。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，字段设为非公共，并添加公共属性或方法返回的字段数据。 LinkDemand 安全检查类型保护对该类型的属性和方法的访问。 但是，代码访问安全性不适用于字段。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 安全问题并获得良好的设计，您应公共字段非公共，从而解决冲突。 如果字段不会保存信息应保持安全，则可以禁止显示此规则的警告，您不依赖于字段的内容。

## <a name="example"></a>示例
 下面的示例组成的库类型 (`SecuredTypeWithFields`) 包含不安全的字段，一种类型 (`Distributor`)，可以创建库类型的实例和错误的传递到类型的实例没有权限来创建它们，和应用程序代码可以读取实例的字段，即使它没有保护类型的权限。

 以下库代码违反了此规则。

 [!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]

## <a name="example-1"></a>示例 1
 由于链接要求保护受保护的类型，该应用程序无法创建实例。 下面的类使应用程序以获取受保护的类型的实例。

 [!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]

## <a name="example-2"></a>示例 2
 以下应用程序演示了如何，如果没有权限访问受保护的类型的方法，代码可以访问其字段。

 [!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]

该示例产生下面的输出：

```txt
Creating an instance of SecuredTypeWithFields.
Secured type fields: 22, 33
Changing secured type's field...
Cached Object fields: 99, 33
```

## <a name="related-rules"></a>相关的规则

- [CA1051:不要声明可见实例字段](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>请参阅

- [链接需求](/dotnet/framework/misc/link-demands)
- [数据和建模](/dotnet/framework/data/index)