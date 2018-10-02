---
title: CA2204： 应正确拼写文本 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 39d841fbfa9be3e3ee5764e986a9688ca4113caf
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587683"
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204：应正确拼写文本
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA2204： 应正确拼写文本](https://docs.microsoft.com/visualstudio/code-quality/ca2204-literals-should-be-spelled-correctly)。

|||
|-|-|
|TypeName|LiteralsShouldBeSpelledCorrectly|
|CheckId|CA2204|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 参数或需要的已本地化的字符串和文字字符串的属性中使用的文本字符串的方法传递包含一个或多个未被 Microsoft 拼写检查器库识别的单词。

## <a name="rule-description"></a>规则说明
 此规则检查的作为值传递到参数或属性时一个文本字符串或多个以下情况下为 true:

-   <xref:System.ComponentModel.LocalizableAttribute>参数或属性的特性设置为 true。

-   参数或属性名称包含"Text"、"Message"描述"。

-   传递给 Console.Write 或 Console.WriteLine 方法将字符串参数名称是"值"format"。

 此规则将文本字符串分析为切分组合词的单词，并检查每个单词/标记的拼写。 有关分析算法的信息，请参阅[CA1704： 标识符应正确拼写](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)。

 默认情况下，使用拼写检查器的英语 (en) 版本。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更正该单词的拼写或将该词添加到自定义字典。 有关如何使用自定义词典的信息，请参阅[如何： 自定义代码分析字典](../code-quality/how-to-customize-the-code-analysis-dictionary.md)。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 正确的拼写的单词可以减少所需的新软件库，学习曲线。

## <a name="related-rules"></a>相关的规则
 [CA1704：标识符应正确拼写](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)

 [CA1703：资源字符串应正确拼写](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)



