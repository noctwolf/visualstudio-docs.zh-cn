---
title: CA1411:COM 注册方法应该是不可见的
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1411
- ComRegistrationMethodsShouldNotBeVisible
helpviewer_keywords:
- ComRegistrationMethodsShouldNotBeVisible
- CA1411
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 39547159f46f4c1921093b020c2bb888e4aecce0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013166"
---
# <a name="ca1411-com-registration-methods-should-not-be-visible"></a>CA1411:COM 注册方法应该是不可见的

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldNotBeVisible|
|CheckId|CA1411|
|类别|Microsoft.Interoperability|
|是否重大更改|重大|

## <a name="cause"></a>原因

使用标记的方法<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName>或<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>属性是外部可见。

## <a name="rule-description"></a>规则说明
 程序集注册时使用组件对象模型 (COM)，条目添加到注册表中的程序集中每个 COM 可见类型。 使用标记的方法<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>和<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>属性在注册和注销过程中，分别称为，若要运行的是特定于注册/注销这些类型的用户代码。 此代码不应在这些进程外部调用。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更改到方法的可访问性`private`或`internal`(`Friend`中[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)])。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例显示与该规则冲突的两种方法。

 [!code-csharp[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/CSharp/ca1411-com-registration-methods-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/VisualBasic/ca1411-com-registration-methods-should-not-be-visible_1.vb)]

## <a name="related-rules"></a>相关的规则
 [CA1410:应对 COM 注册方法进行匹配](../code-quality/ca1410-com-registration-methods-should-be-matched.md)

## <a name="see-also"></a>请参阅

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [向 COM 注册程序集](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe（程序集注册工具）](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)