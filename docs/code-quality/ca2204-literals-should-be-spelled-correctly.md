---
title: CA2204：应正确拼写文本
ms.date: 03/28/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81989ebce0319669a03d62a504f87a0500400cd9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204：应正确拼写文本

|||
|-|-|
|TypeName|LiteralsShouldBeSpelledCorrectly|
|CheckId|CA2204|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

文字字符串传递作为自变量的可本地化的参数，或可本地化属性，并且该字符串包含一个或多个未被 Microsoft 拼写检查器库识别的单词。

## <a name="rule-description"></a>规则说明

此规则检查的文本字符串，作为值传递给参数或属性时一个或多个以下情况下为真：

- <xref:System.ComponentModel.LocalizableAttribute>参数或属性的属性设置为 true。

- 参数或属性名称包含"Text"、"消息"标题"。

- 传递到的字符串变量的名称<xref:System.Console.Write%2A>或<xref:System.Console.WriteLine>方法为"value"format"。

此规则将文本字符串解析成单词，将拆分为标记复合词，并检查每个单词或令牌的拼写。 有关分析算法的信息，请参阅[CA1704： 标识符应正确拼写](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)。

## <a name="language"></a>语言

只对基于英语区域性字典当前检查拼写检查器。 你可以通过添加更改你的项目的项目文件中的区域性**CodeAnalysisCulture**元素。

例如：

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> 如果你将区域性设置为基于英语区域性之外的任何内容时，会以无提示方式禁用此代码分析规则。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复与此规则的冲突，更正该单词的拼写或添加到自定义词典的单词。 有关如何使用自定义词典的信息，请参阅[如何： 自定义代码分析字典](../code-quality/how-to-customize-the-code-analysis-dictionary.md)。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。 正确的拼写的单词可以减少所需的新软件库学习曲线。

## <a name="related-rules"></a>相关的规则

- [CA1704：标识符应正确拼写](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA1703：资源字符串应正确拼写](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)