---
title: CA1409:COM 可见类型应该是可创建的
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 05dbe964a16f838088fe8b053d59c1916daf38f7
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55933713"
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409:COM 可见类型应该是可创建的

|||
|-|-|
|TypeName|ComVisibleTypesShouldBeCreatable|
|CheckId|CA1409|
|类别|Microsoft.Interoperability|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 专门标记为可见到组件对象模型 (COM) 的引用类型包含公共的参数化构造函数，但不包含公共的默认 （无参数） 构造函数。

## <a name="rule-description"></a>规则说明
 不能由 COM 客户端创建没有公共默认构造函数的类型。 但是，可以仍访问类型的 COM 客户端如果另一种方法可用于创建类型并将其传递给客户端 （例如，通过方法调用的返回值）。

 规则将忽略类型派生自<xref:System.Delegate?displayProperty=fullName>。

 默认情况下，以下是对 COM 可见： 程序集、 公共类型、 公共类型中的公共实例成员和公共值类型的所有成员。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，将公共默认构造函数添加或删除<xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>的类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告，如果提供了其他方法来创建并将该对象传递给 COM 客户端。

## <a name="related-rules"></a>相关的规则
 [CA1017:用 ComVisibleAttribute 标记程序集](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>请参阅

- [为互操作限定 .NET 类型](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
- [与非托管代码交互操作](/dotnet/framework/interop/index)