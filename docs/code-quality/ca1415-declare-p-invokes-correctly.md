---
title: 'CA1415: P 调用正确声明'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eb03f6a5e0242af79242f2b3ae735fa4df694c20
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415：正确声明 P/Invoke
|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|类别|Microsoft.Interoperability|
|是否重大更改|无间断-如果将参数声明 P/Invoke 无法程序集外可见。 中断性-如果将参数声明 P/Invoke 可以程序集外可见。|

## <a name="cause"></a>原因
 平台调用方法未正确声明。

## <a name="rule-description"></a>规则说明
 平台调用方法访问非托管的代码，而且使用定义`Declare`中的关键字[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]或<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>。 目前，此规则查找针对平台调用目标有一个指针指向 OVERLAPPED 结构参数的 Win32 函数的方法声明和对应的托管的参数不是一个指向<xref:System.Threading.NativeOverlapped?displayProperty=fullName>结构。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，正确声明平台调用方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 平台调用方法，与该规则冲突并满足该规则的以下示例所示。

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]

## <a name="see-also"></a>请参阅
 [与非托管代码交互操作](/dotnet/framework/interop/index)