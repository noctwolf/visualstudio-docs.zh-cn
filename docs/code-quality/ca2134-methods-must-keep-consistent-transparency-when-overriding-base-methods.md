---
title: CA2134:在重写基方法时，方法必须保持一致的透明度
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ca28f364307d4a2b73235bc6541cb8aa01abd56
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920657"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134:在重写基方法时，方法必须保持一致的透明度

|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
当用标记的方法替代透明或<xref:System.Security.SecurityCriticalAttribute> <xref:System.Security.SecuritySafeCriticalAttribute>用标记的方法时, 将触发此规则。 当透明或用<xref:System.Security.SecuritySafeCriticalAttribute>标记的方法覆盖<xref:System.Security.SecurityCriticalAttribute>用标记的方法时, 也会触发规则。

该规则在重写虚方法或实现接口时应用。

## <a name="rule-description"></a>规则说明
此规则在尝试更改继承链中的方法的安全性可访问性时引发。 例如, 如果基类中的虚方法是透明的或安全关键的, 则派生类必须使用透明的或安全关键的方法来重写它。 相反, 如果虚拟是安全关键的, 则派生类必须使用安全关键方法对其进行重写。 相同的规则适用于实现接口方法。

当在 JIT 编译代码而不是运行时, 将强制执行透明度规则, 以使透明度计算不包含动态类型信息。 因此, 无论动态类型如何, 透明度计算的结果都必须能够完全根据 JIT 编译的静态类型确定。

## <a name="how-to-fix-violations"></a>如何解决冲突
若要修复与此规则的冲突, 请更改重写虚方法或实现接口的方法的透明度, 以匹配虚拟或接口方法的透明度。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
请勿禁止显示此规则的警告。 违反此规则会导致使用2级透明度<xref:System.TypeLoadException>的程序集的运行时。

## <a name="examples"></a>示例

### <a name="code"></a>代码
[!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]

## <a name="see-also"></a>请参阅
[安全透明代码, 级别2](/dotnet/framework/misc/security-transparent-code-level-2)