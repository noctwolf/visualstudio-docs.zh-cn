---
title: CA2221：终结器应受到保护
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2221
- FinalizersShouldBeProtected
helpviewer_keywords:
- FinalizersShouldBeProtected
- CA2221
ms.assetid: bda03aee-4cce-45d3-907d-17f4ee030acc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf4ee1aef9ef31dccad5a9728244aeaf79f9e6a4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca2221-finalizers-should-be-protected"></a>CA2221：终结器应受到保护
|||
|-|-|
|TypeName|FinalizersShouldBeProtected|
|CheckId|CA2221|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 公共类型实现一个并不指定系列 （受保护） 的访问的终结器。

## <a name="rule-description"></a>规则说明
 终结器必须使用族访问修饰符。 通过 C#、 Visual Basic 和 Visual c + + 编译器强制执行此规则。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，更改终结器可访问系列。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 不能在任何高级的.NET 语言; 中违反此规则如果你正在编写 Microsoft 中间语言，它可以违反了。

```
// =============== CLASS MEMBERS DECLARATION ===================
//   note that class flags, 'extends' and 'implements' clauses
//          are provided here for information only

.namespace UsageLibrary
{
  .class public auto ansi beforefieldinit FinalizeMethodNotProtected
         extends [mscorlib]System.Object
  {
    .method public hidebysig instance void
            Finalize() cil managed
    {

      // Code size       1 (0x1)
      .maxstack  0
      IL_0000:  ret
    } // end of method FinalizeMethodNotProtected::Finalize

    .method public hidebysig specialname rtspecialname
            instance void  .ctor() cil managed
    {
      // Code size       7 (0x7)
      .maxstack  1
      IL_0000:  ldarg.0
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
      IL_0006:  ret
    } // end of method FinalizeMethodNotProtected::.ctor

  } // end of class FinalizeMethodNotProtected
} // end of namespace
```

## <a name="see-also"></a>请参阅
 [释放模式](/dotnet/standard/design-guidelines/dispose-pattern)