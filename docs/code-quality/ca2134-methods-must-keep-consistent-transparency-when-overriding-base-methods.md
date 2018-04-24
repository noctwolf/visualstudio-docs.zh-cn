---
title: CA2134：在重写基方法时，方法必须保持一致的透明度
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e74eee5098b23d5e0adf94259aa6ce0b9f2f423e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134：在重写基方法时，方法必须保持一致的透明度
|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 当的方法标记为引发此规则<xref:System.Security.SecurityCriticalAttribute>重写一个透明的或用标记的方法<xref:System.Security.SecuritySafeCriticalAttribute>。 是透明的或与标记的方法时，还会引发此规则<xref:System.Security.SecuritySafeCriticalAttribute>重写方法将标有<xref:System.Security.SecurityCriticalAttribute>。

 该规则在重写虚方法或实现接口时应用。

## <a name="rule-description"></a>规则说明
 在尝试更改进一步继承链向上的方法的安全可访问性引发此规则。 例如，如果透明或安全关键，基类中的虚拟方法，然后派生的类必须重写它使用透明或安全关键方法。 相反，如果虚拟是安全关键的派生的类必须重写它使用安全关键方法。 同一规则适用于实现接口方法。

 执行代码的 JIT 编译时而不是在运行时，以便透明度计算没有动态类型信息，则会强制执行透明度规则。 因此，透明度计算结果必须能够确定仅从受 JIT 编译的而不考虑动态类型的静态类型。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，更改是重写虚拟方法或实现透明虚拟或接口方法相匹配的接口的方法的透明度。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不要禁止显示此规则的警告。 违反此规则将导致运行时<xref:System.TypeLoadException>使用 2 级透明度的程序集。

## <a name="examples"></a>示例

### <a name="code"></a>代码
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]

## <a name="see-also"></a>请参阅
 [安全透明的代码，级别 2](/dotnet/framework/misc/security-transparent-code-level-2)