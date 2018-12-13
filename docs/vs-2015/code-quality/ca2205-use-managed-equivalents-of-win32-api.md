---
title: CA2205： 使用托管的 Win32 API 的等效项 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
helpviewer_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
ms.assetid: 1c65ab59-3e50-4488-a727-3969c7f6cbe4
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ba23b176ed4f2120f4675611567955bdaf652153
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49907464"
---
# <a name="ca2205-use-managed-equivalents-of-win32-api"></a>CA2205：使用 Win32 API 的托管等效项
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseManagedEquivalentsOfWin32Api|
|CheckId|CA2205|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 平台调用定义方法和具有等效功能的方法中存在[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]类库。

## <a name="rule-description"></a>规则说明
 平台调用方法用于调用非托管的 DLL 函数，并使用定义<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>属性，或`Declare`在 Visual Basic 中的关键字。 定义不正确的平台调用方法可能会导致运行时异常到由于问题，例如名不符实了函数、 错误的参数和返回值数据类型和不正确的字段规范，如调用约定和字符映射设置。 如果可用，它通常是容易调用等效的托管的方法比定义并直接调用非托管的方法更简单、 更少出错。 调用平台调用方法可能还会导致需要解决的其他安全问题。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，请对非托管函数的调用替换为通过调用其托管等同项。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果建议的替代方法不提供所需的功能，禁止显示此规则的警告。

## <a name="example"></a>示例
 下面的示例演示一个平台的调用违反了此规则的方法定义。 此外，对平台调用调用方法并显示等效的托管的方法。

 [!code-csharp[FxCop.Usage.ManagedEquivalents#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ManagedEquivalents/cs/FxCop.Usage.ManagedEquivalents.cs#1)]
 [!code-vb[FxCop.Usage.ManagedEquivalents#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.ManagedEquivalents/vb/FxCop.Usage.ManagedEquivalents.vb#1)]

## <a name="related-rules"></a>相关的规则
 [CA1404：紧接在 P/Invoke 之后调用 GetLastError](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)

 [CA1060：将 P/Invoke 移动到](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md) NativeMethods 类

 [CA1400：P/Invoke 入口点应该存在](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

 [CA1401：P/Invokes 应为不可见](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

 [CA2101：指定对 P/Invoke 字符串参数进行封送处理](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)



