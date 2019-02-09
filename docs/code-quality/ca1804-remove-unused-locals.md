---
title: CA1804:移除未使用的局部变量
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f567fa1d1f793395532efac5991b01c5087b638a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55908525"
---
# <a name="ca1804-remove-unused-locals"></a>CA1804:移除未使用的局部变量

|||
|-|-|
|TypeName|RemoveUnusedLocals|
|CheckId|CA1804|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 方法声明本地变量，但不使用除变量可能是作为接收方的赋值语句。 有关此规则分析，必须使用调试信息生成测试的程序集和关联的程序数据库 (.pdb) 文件必须可用。

## <a name="rule-description"></a>规则说明
 未使用的局部变量和不必要的赋值会增加程序集的大小并降低性能。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除或使用本地变量。 请注意，C# 编译器的是附带[!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]删除未使用的本地变量时`optimize`选项处于启用状态。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果变量是编译器发出，禁止显示此规则的警告。 如果性能和代码维护不关注的主要问题，则也可以禁止显示此规则的警告或禁用规则，安全。

## <a name="example"></a>示例
 下面的示例显示了多个未使用的本地变量。

 [!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
 [!code-csharp[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA1809:避免过多的局部变量](../code-quality/ca1809-avoid-excessive-locals.md)

 [CA1811:避免使用未调用的私有代码](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812:避免未实例化的内部类](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801:检查未使用的参数](../code-quality/ca1801-review-unused-parameters.md)