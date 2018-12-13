---
title: CA1410：应对 COM 注册方法进行匹配
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5d04668ef21ea469e1dbb42cea6c8a8b5b7f18f5
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47858395"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410：应对 COM 注册方法进行匹配

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldBeMatched|
|CheckId|CA1410|
|类别|Microsoft.Interoperability|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 某个类型声明与标记的方法<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName>属性，但不声明具有标记的方法<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>属性，反之亦然。

## <a name="rule-description"></a>规则说明
 对于要创建.NET Framework 类型的组件对象模型 (COM) 客户端，必须首先注册该类型。 如果可用，使用标记的方法<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>在注册过程中运行用户指定的代码调用属性。 使用标记的相应方法<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>属性被称为在注销过程中要反转的注册方法的操作。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请添加相应的注册或注销方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例显示了违反了此规则的类型。 注释的代码显示了对冲突的修复。

 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]

## <a name="related-rules"></a>相关的规则
 [CA1411：COM 注册方法应该是不可见的](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)

## <a name="see-also"></a>请参阅

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [向 COM 注册程序集](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe（程序集注册工具）](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)