---
title: CA1014：用 CLSCompliantAttribute 标记程序集
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51e5a43a402bb215a939b37354dd30f24e4d5d14
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014：用 CLSCompliantAttribute 标记程序集
|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|类别|Microsoft.Design|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 程序集没有<xref:System.CLSCompliantAttribute?displayProperty=fullName>特性应用于它。

## <a name="rule-description"></a>规则说明
 公共语言规范 (CLS) 定义了程序集在跨编程语言使用时必须符合的命名限制、数据类型和规则。 合理的设计指出程序的所有程序集将显式指示 CLS 遵从性与<xref:System.CLSCompliantAttribute>。 如果该属性不存在的程序集，程序集即不合规。

 它有可能包含类型或类型成员不符合 cls 的程序集。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，将添加到程序集的属性。 而不是标记为不符合要求的整个程序集，你应确定哪些类型或类型成员不符合并将这些元素在这种标记。 如果可能，应为不符合的成员提供符合 cls 的替代方法，以便尽可能多的用户可以访问您的程序集的所有功能。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 如果你不想要符合的程序集，应用该特性并将其值设置为`false`。

## <a name="example"></a>示例
 下面的示例演示具有的程序集<xref:System.CLSCompliantAttribute?displayProperty=fullName>应用声明它符合 CLS 的特性。

 [!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]

## <a name="see-also"></a>请参阅
 <xref:System.CLSCompliantAttribute?displayProperty=fullName> [语言独立性和独立于语言的组件](/dotnet/standard/language-independence-and-language-independent-components)