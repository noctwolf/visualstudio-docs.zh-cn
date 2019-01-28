---
title: CA2223:成员不应只是返回类型不同
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- MembersShouldDifferByMoreThanReturnType
- CA2223
helpviewer_keywords:
- CA2223
- MembersShouldDifferByMoreThanReturnType
ms.assetid: eb326d9f-50d9-48cb-84be-d41c84a8fe09
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b600ff987d4a1e723b3ca1c7fabb97246f61322d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960745"
---
# <a name="ca2223-members-should-differ-by-more-than-return-type"></a>CA2223:成员不应只是返回类型不同

|||
|-|-|
|TypeName|MembersShouldDifferByMoreThanReturnType|
|CheckId|CA2223|
|类别|Microsoft.Usage|
|是否重大更改|重大|

## <a name="cause"></a>原因
 两个公共或受保护成员具有除返回类型完全相同的签名。

## <a name="rule-description"></a>规则说明
 虽然公共语言运行时允许的返回类型区分其余部分都相同的成员使用，此功能不在公共语言规范中，也不是.NET 编程语言中的常见功能。 当成员只是返回类型不同时，开发人员和开发工具可能不正确区分它们。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更改成员的设计，以便它们都是唯一仅根据其名称和参数类型或不公开这些成员。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 以下示例中，在 Microsoft 中间语言 (MSIL) 中显示了违反此规则的类型。 请注意，不能通过使用 C# 或 Visual Basic 违反此规则。

```
.namespace UsageLibrary
{
  .class public auto ansi beforefieldinit ReturnTypeTest
         extends [mscorlib]System.Object
  {
    .method public hidebysig instance int32
            AMethod(int32 x) cil managed
    {
      // Code size       6 (0x6)
      .maxstack  1
      .locals init (int32 V_0)
      IL_0000:  ldc.i4.0
      IL_0001:  stloc.0
      IL_0002:  br.s       IL_0004

      IL_0004:  ldloc.0
      IL_0005:  ret
    } // end of method ReturnTypeTest::AMethod

    .method public hidebysig instance string
            AMethod(int32 x) cil managed
    {
      // Code size       10 (0xa)
      .maxstack  1
      .locals init (string V_0)
      IL_0000:  ldstr      "test"
      IL_0005:  stloc.0
      IL_0006:  br.s       IL_0008

      IL_0008:  ldloc.0
      IL_0009:  ret
    } // end of method ReturnTypeTest::AMethod

    .method public hidebysig specialname rtspecialname
            instance void  .ctor() cil managed
    {
      // Code size       7 (0x7)
      .maxstack  1
      IL_0000:  ldarg.0
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
      IL_0006:  ret
    } // end of method ReturnTypeTest::.ctor

  } // end of class ReturnTypeTest

} // end of namespace UsageLibrary
```