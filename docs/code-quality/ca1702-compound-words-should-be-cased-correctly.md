---
title: CA1702：复合词应采用正确的大小写
ms.date: 03/28/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
helpviewer_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
ms.assetid: 05481245-7ad8-48c3-a456-3aa44b6160a6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 977273299e0ae403a3d93501b8879c36096c7c7c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1702-compound-words-should-be-cased-correctly"></a>CA1702：复合词应采用正确的大小写

|||
|-|-|
|TypeName|CompoundWordsShouldBeCasedCorrectly|
|CheckId|CA1702|
|类别|Microsoft.Naming|
|是否重大更改|对程序集，换行时引发。<br /><br /> 无间断-如果对类型参数引发。|

## <a name="cause"></a>原因

标识符的名称包含多个单词，其中至少有一个单词似乎是大小写不正确的组合词。

## <a name="rule-description"></a>规则说明

标识符名称拆分为单词根据大小写。 由 Microsoft 拼写检查器库，每个连续的两个 word 组合进行检查。 如果被识别，该标识符将生成与规则的冲突。 导致冲突的复合词的示例包括"校验和"和"多部分"大小写应当为"Checksum"和"Multipart"，分别。 由于以前的常见用法，几个例外内置规则，并标记一些单个的词，如"工具栏"和"Filename"，该大小写应当作为 （在此情况下，"工具栏"和"FileName"） 的两个不同的单词。

命名约定提供了通用的外观的库，面向公共语言运行时。 这减少了学习曲线，才能使用新的软件库和客户更有信心库由在开发的托管代码中有专业技能的人员。

## <a name="how-to-fix-violations"></a>如何解决冲突

更改名称，以便它正确的大小写。

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

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

则可以安全地禁止显示此规则的警告，如果由拼写字典中，识别的组合词两个部件，目的是使用两个单词。

## <a name="related-rules"></a>相关的规则

- [CA1701：资源字符串复合词应采用正确的大小写](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1709：标识符的大小写应当正确](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708：标识符不应仅以大小写进行区分](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

## <a name="see-also"></a>请参阅

- [命名规则](/dotnet/standard/design-guidelines/naming-guidelines)
- [大小写约定](/dotnet/standard/design-guidelines/capitalization-conventions)