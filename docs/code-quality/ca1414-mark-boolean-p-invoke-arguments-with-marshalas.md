---
title: CA1414：用 MarshalAs 标记布尔型 P-Invoke 参数
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a5936c07646201ab3988dd7cc792f758ed698063
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548948"
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414：用 MarshalAs 标记布尔型 P/Invoke 参数

|||
|-|-|
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|
|CheckId|CA1414|
|类别|Microsoft.Interoperability|
|是否重大更改|重大|

## <a name="cause"></a>原因
 平台调用方法声明中包括<xref:System.Boolean?displayProperty=fullName>参数或返回值，但<xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName>属性不应用于参数或返回值。

## <a name="rule-description"></a>规则说明
 将平台调用方法访问非托管的代码与使用定义`Declare`中的关键字[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]或<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>。 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 指定用于托管和非托管代码之间转换数据类型的封送处理行为。 很多简单数据类型，如<xref:System.Byte?displayProperty=fullName>和<xref:System.Int32?displayProperty=fullName>、 在非托管代码中有一种表示形式和不需要其封送处理行为的规范; 公共语言运行时自动提供正确的行为。

 <xref:System.Boolean>数据类型在非托管代码中有多种表示形式。 当<xref:System.Runtime.InteropServices.MarshalAsAttribute>未指定，默认封送处理行为<xref:System.Boolean>数据类型是<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>。 这是一个 32 位整数，不是适用于所有情况。 所需的非托管方法的布尔值表示应进行确定和匹配到适当<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>。 UnmanagedType.Bool 是 Win32 BOOL 类型，它始终为 4 个字节。 UnmanagedType.U1 应该用于 c + +`bool`或其他 1 字节类型。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请应用<xref:System.Runtime.InteropServices.MarshalAsAttribute>到<xref:System.Boolean>参数或返回值。 将属性的值设置为相应<xref:System.Runtime.InteropServices.UnmanagedType>。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 即使是合适的默认封送处理行为，当显式指定行为更轻松地维护代码。

## <a name="example"></a>示例

平台调用标记有适当的方法的以下示例所示<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性。

 [!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CSharp/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cs)]
 [!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/VisualBasic/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.vb)]
 [!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CPP/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cpp)]

## <a name="related-rules"></a>相关的规则
 [CA1901：P/Invoke 声明应为可移植声明](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)

 [CA2101：指定对 P/Invoke 字符串参数进行封送处理](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

## <a name="see-also"></a>请参阅

- <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>
- [与非托管代码交互操作](/dotnet/framework/interop/index)