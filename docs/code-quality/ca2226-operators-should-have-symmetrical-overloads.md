---
title: CA2226:运算符应有对称重载
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
helpviewer_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a903fbd3b01523a86302b58f8e9a74917312566c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541726"
---
# <a name="ca2226-operators-should-have-symmetrical-overloads"></a>CA2226:运算符应有对称重载

|||
|-|-|
|TypeName|OperatorsShouldHaveSymmetricalOverloads|
|CheckId|CA2226|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

某个类型实现了相等运算符或不等运算符，却未实现相反运算符。

默认情况下，此规则只看起来在外部可见的类型，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

有任何情况下，其中等式或不等式是适用于某种类型的实例，未定义相反运算符。 类型通常通过返回的相反的值的相等运算符实现不等运算符。

C# 编译器会发出有关此规则冲突错误。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要解决此规则的冲突，可实现相等和不相等运算符或删除的存在。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。 如果这样做，您的类型不会与.NET 是一致的方式。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca2226.api_surface = private, internal
```

此类别 （用法） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="related-rules"></a>相关的规则

- [CA1046:请重载相等运算符对引用类型](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2225:运算符重载具有命名的备用项](../code-quality/ca2225-operator-overloads-have-named-alternates.md)
- [CA2224:重写 equals 方法重载相等运算符](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218:重写 Equals 时重写 GetHashCode](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)
- [CA2231：重写 ValueType.Equals 时应重载相等运算符](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)