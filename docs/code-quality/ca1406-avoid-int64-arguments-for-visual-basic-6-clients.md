---
title: CA1406:避免对 Visual Basic 6 客户端使用 Int64 参数
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7be9df5658e3f68c5d5f03b356c60c7ab023ed46
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043162"
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406:避免对 Visual Basic 6 客户端使用 Int64 参数

|||
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|类别|Microsoft.Interoperability|
|是否重大更改|重大|

## <a name="cause"></a>原因
 专门标记为可见到组件对象模型 (COM) 的类型声明的成员，采用<xref:System.Int64?displayProperty=fullName>参数。

## <a name="rule-description"></a>规则说明
 Visual Basic 6 COM 客户端不能访问 64 位整数。

 默认情况下，以下是对 COM 可见： 程序集、 公共类型、 公共类型中的公共实例成员和公共值类型的所有成员。 但是，若要减少误报，此规则要求类型来显式声明; COM 可见的性包含程序集必须使用标记<xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>设置为`false`和类型必须标有<xref:System.Runtime.InteropServices.ComVisibleAttribute>设置为`true`。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则为其值始终可以表示为 32 位整型参数的冲突，将参数类型更改为<xref:System.Int32?displayProperty=fullName>。 如果参数的值可能大于可表示为 32 位整数，将参数类型更改为<xref:System.Decimal?displayProperty=fullName>。 请注意，这两<xref:System.Single?displayProperty=fullName>并<xref:System.Double?displayProperty=fullName>丢失精度的上限范围的<xref:System.Int64>数据类型。 如果该成员不打算对 COM 可见，请将其与标记<xref:System.Runtime.InteropServices.ComVisibleAttribute>设置为`false`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告，如果它是某些 Visual Basic 6 COM 客户端将不访问类型。

## <a name="example"></a>示例
 下面的示例显示了违反了此规则的类型。

 [!code-csharp[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/CSharp/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.cs)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/VisualBasic/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.vb)]

## <a name="related-rules"></a>相关的规则
 [CA1413:避免在 COM 可见值类型中的非公共字段](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407:避免在 COM 可见类型中的静态成员](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017:用 ComVisibleAttribute 标记程序集](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>请参阅

- [与非托管代码交互操作](/dotnet/framework/interop/index)
- [Long 数据类型](/dotnet/visual-basic/language-reference/data-types/long-data-type)