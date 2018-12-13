---
title: CA1505： 避免编写无法维护的代码 |Microsoft Docs
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
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 089a4d45c74b1849a73c99c8065f1f67ca9b0e43
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49906099"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505：避免编写无法维护的代码
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|类别|Microsoft.Maintainability|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 类型或方法具有较低的可维护性索引值。

## <a name="rule-description"></a>规则说明
 通过使用以下度量值计算的可维护性索引： 行代码，程序卷和圈复杂度。 程序卷是了解类型或方法的运算符和操作数在代码中的数量为基础的难易程度的度量值。 圈复杂度是复杂性的度量值的类型或方法的结构化。 您可以了解有关代码的指标的详细信息[测量复杂性和托管代码可维护性](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)。

 较低的可维护性索引指示类型或方法可能难以维护而且可能会重新设计的良好候选项。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此冲突，重新设计的类型或方法，并尝试将其拆分为较小且更集中的类型或方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果类型或方法仍被视为可维护，尽管其尺寸大或者不能拆分的类型或方法，请排除此警告。

## <a name="see-also"></a>请参阅
 [可维护性警告](../code-quality/maintainability-warnings.md)[测量复杂性和可维护性的托管代码](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



