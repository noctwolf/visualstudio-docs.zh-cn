---
title: CA1708： 标识符应差别不仅仅在于大小写 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 91e35518fe274255727975d589a32a1b0342e320
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49901770"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708：标识符不应仅以大小写进行区分
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因
 两种类型、 成员、 参数或完全限定的命名空间的名称是相同的如果将它们转换为小写。

## <a name="rule-description"></a>规则说明
 不能仅通过大小写区分命名空间、类型、成员和参数的标识符，因为针对公共语言运行时的语言不需要区分大小写。 例如，[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]是一种广泛使用的不区分大小写语言。

 公开可见的成员将引发此规则。

## <a name="how-to-fix-violations"></a>如何解决冲突
 选择时就与其他标识符的比较不区分大小写的方式是唯一的名称。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 库可能不能使用所有可用语言中[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]。

## <a name="example-of-a-violation"></a>冲突的示例
 下面的示例演示了此规则的冲突。

 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Naming.IdentifiersShouldDifferByMoreThanCase/cs/FxCop.Naming.IdentifiersShouldDifferByMoreThanCase.cs#1)]

## <a name="related-rules"></a>相关的规则
 [CA1709：标识符的大小写应当正确](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)



