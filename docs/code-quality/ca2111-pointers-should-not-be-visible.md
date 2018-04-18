---
title: CA2111： 指针不应是可见 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- PointersShouldNotBeVisible
- CA2111
helpviewer_keywords:
- CA2111
- PointersShouldNotBeVisible
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ce027b8e6bcf39623e07a862d4f9fb23c33b9967
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca2111-pointers-should-not-be-visible"></a>CA2111：指针应为不可见
|||  
|-|-|  
|TypeName|PointersShouldNotBeVisible|  
|CheckId|CA2111|  
|类别|Microsoft.Security|  
|是否重大更改|重大|  
  
## <a name="cause"></a>原因  
 公共或受保护<xref:System.IntPtr?displayProperty=fullName>或<xref:System.UIntPtr?displayProperty=fullName>字段不是只读的。  
  
## <a name="rule-description"></a>规则说明  
 <xref:System.IntPtr> 和<xref:System.UIntPtr>均是用于访问非托管的内存的指针类型。 如果指针不是私有、 内部或只读的恶意代码可以更改指针，有可能访问的内存中的任意位置或导致应用程序或系统故障的值。  
  
 如果你想对包含指针字段的类型安全访问权限，请参阅[CA2112： 受保护的类型不应公开字段](../code-quality/ca2112-secured-types-should-not-expose-fields.md)。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 只读的、 内部或私有变得更加安全的指针。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 如果您不依赖于指针的值，禁止显示此规则的警告。  
  
## <a name="example"></a>示例  
 下面的代码演示与冲突，并满足该规则的指针。 请注意非私有指针还违反规则[CA1051： 不要声明可见实例字段](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)。  
  
 [!code-csharp[FxCop.Security.PointersArePrivate#1](../code-quality/codesnippet/CSharp/ca2111-pointers-should-not-be-visible_1.cs)]  
  
## <a name="related-rules"></a>相关的规则  
 [CA2112：受保护的类型不应公开字段](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA1051：不要声明可见实例字段](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>