---
title: CA1405:COM 可见类型的基类型应对 COM 可见
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 65bddd599bb544e000ca1d1269b84e53f51843bb
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918554"
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405:COM 可见类型的基类型应对 COM 可见

|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|类别|Microsoft.Interoperability|
|是否重大更改|DependsOnFix|

## <a name="cause"></a>原因
 组件对象模型 (COM) 可见类型派生自不是 COM 可见类型。

## <a name="rule-description"></a>规则说明
 当 COM 可见类型中的新版本中添加成员时，它必须遵守严格的指导原则，以避免中断绑定到当前版本的 COM 客户端。 对 COM 不可见的类型会假定它不需要添加新成员时，请遵循这些 COM 版本控制规则。 但是，如果 COM 可见类型派生自 COM 不可见类型中，公开的类接口<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName>或<xref:System.Runtime.InteropServices.ClassInterfaceType>（默认值） 的基类型的所有公共成员 （除非它们专门标记为 COM 不可见，这是冗余）向 COM 公开 如果基类型在后续版本中添加新成员，可能会中断将绑定到派生类型的类接口的任何 COM 客户端。 COM 可见类型应该派生 COM 可见类型，以降低中断 COM 客户端的可能性。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，则使 COM 可见的基类型或派生的类型对于 COM 不可见。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例显示了违反了此规则的类型。

 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]

## <a name="see-also"></a>请参阅

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>
- [与非托管代码交互操作](/dotnet/framework/interop/index)