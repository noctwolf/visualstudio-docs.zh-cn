---
title: CA1401：P-Invokes 应为不可见
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9c1d4d9cc5e1550dee87609e5ef0e99dcd9d0cf5
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548616"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401：P/Invokes 应该是不可见的

|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|类别|Microsoft.Interoperability|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或受保护方法的公共类型中具有<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>属性 (也由实现`Declare`中的关键字[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)])。

## <a name="rule-description"></a>规则说明
 使用标记的方法<xref:System.Runtime.InteropServices.DllImportAttribute>属性 (或通过使用定义的方法`Declare`中的关键字[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 使用平台调用服务来访问非托管的代码。 这些方法不能公开。 通过私有或内部保留这些方法，请确保您的库不能用来通过允许访问它们可以其他方式调用的非托管 Api 的调用方破坏安全性。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更改该方法的访问级别。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例声明与此规则冲突的方法。

 [!code-vb[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/VisualBasic/ca1401-p-invokes-should-not-be-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/CSharp/ca1401-p-invokes-should-not-be-visible_1.cs)]