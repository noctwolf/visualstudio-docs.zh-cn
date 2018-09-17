---
title: CA2104：不要声明只读可变引用类型
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 80d40dd60b0a6b6e507b903fd7a6185c5419422e
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551683"
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104：不要声明只读可变引用类型

|||
|-|-|
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|
|CheckId|CA2104|
|类别|Microsoft.Security|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 外部可见类型包含外部可见的只读字段，该字段为可变的引用类型。

## <a name="rule-description"></a>规则说明
 可变类型是实例数据可被修改的类型。 <xref:System.Text.StringBuilder?displayProperty=fullName>类是可变引用类型的一个示例。 它包含可以更改的类的实例值的成员。 不可变的引用类型的一个示例是<xref:System.String?displayProperty=fullName>类。 已实例化后，其值可能永远不会更改。

 只读修饰符 ([readonly](/dotnet/csharp/language-reference/keywords/readonly)在 C# 中， [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly)中[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]，和[const](/cpp/cpp/const-cpp) c + + 中) 上的引用类型字段 （c + + 中的指针） 防止字段替换为引用类型的不同实例。 但是，修饰符不会阻止通过引用类型进行修改的字段的实例数据。

 只读数组字段不受此规则，但是会导致违反[CA2105： 数组字段不应为只读](../code-quality/ca2105-array-fields-should-not-be-read-only.md)规则。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除只读修饰符，或接受一项重大更改时，该字段将替换为不可变类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告，如果字段类型是不可变。

## <a name="example"></a>示例
 下面的示例演示了一个导致该规则的冲突的字段声明。

 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]