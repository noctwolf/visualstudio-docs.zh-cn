---
title: CA1708：标识符不应仅以大小写进行区分
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 543763049a297a41d2c424da378d486f910f5e1a
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45552053"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708：标识符不应仅以大小写进行区分
|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因
 两种类型、 成员、 参数或完全限定的命名空间的名称是相同的如果将它们转换为小写。

## <a name="rule-description"></a>规则说明
 不能仅通过大小写区分命名空间、类型、成员和参数的标识符，因为针对公共语言运行时的语言不需要区分大小写。 例如，[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]是一种广泛使用的不区分大小写语言。

 公开可见的成员将引发此规则。

## <a name="how-to-fix-violations"></a>如何解决冲突
 选择时就与其他标识符的比较不区分大小写的方式是唯一的名称。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 库可能不能使用所有可用语言中[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]。

## <a name="example-of-a-violation"></a>冲突的示例
 下面的示例演示了此规则的冲突。

 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA1709：标识符的大小写应当正确](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)