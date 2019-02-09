---
title: CA1404:紧接在 P-Invoke 之后调用 GetLastError
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2cd6e3228d67b8dd04cda15549f6b1d172d02916
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55919074"
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404:紧接在 P/Invoke 之后调用 GetLastError

|||
|-|-|
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|
|CheckId|CA1404|
|类别|Microsoft.Interoperability|
|是否重大更改|非换行|

## <a name="cause"></a>原因

调用<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName>方法或等效 Win32`GetLastError`函数，并调用紧邻的前不到的平台调用方法。

## <a name="rule-description"></a>规则说明
 将平台调用方法访问非托管的代码与使用定义`Declare`中的关键字[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]或<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>属性。 通常情况下，如果失败，非托管的函数调用 Win32`SetLastError`函数设置为与下列失败关联的错误代码。 失败的函数的调用方调用 Win32`GetLastError`函数检索错误代码，并确定失败的原因。 错误代码在每个线程的基础上进行维护和的后续调用会覆盖`SetLastError`。 托管的代码的调用失败的平台调用方法后，可以通过调用检索错误代码<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>方法。 因为错误代码时可以覆盖其他托管的类的库方法，从内部调用`GetLastError`或<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>的平台调用方法调用后立即应调用方法。

 规则将忽略对以下调用托管的成员之间对平台调用发生时调用方法和调用<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>。 这些成员未更改的错误代码，可用于确定某个平台的成功调用的方法调用。

- <xref:System.IntPtr.Zero?displayProperty=fullName>

- <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>

- <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请将移动到调用<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>，使其紧跟在平台调用调用方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 则可以安全地禁止显示此规则的警告，如果在平台之间的代码调用方法调用和<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>方法调用不能显式或隐式导致要更改的错误代码。

## <a name="example"></a>示例
 下面的示例演示与规则冲突的方法和满足该规则的方法。

 [!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/VisualBasic/ca1404-call-getlasterror-immediately-after-p-invoke_1.vb)]
 [!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/CSharp/ca1404-call-getlasterror-immediately-after-p-invoke_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA1060:将 P/Invoke 移动到 NativeMethods 类](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

 [CA1400:P/Invoke 入口点应该存在](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

 [CA1401:P/Invokes 应该是不可见](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

 [CA2101:指定对 P/Invoke 字符串自变量封送处理](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

 [CA2205:使用 Win32 API 的托管等效项](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)