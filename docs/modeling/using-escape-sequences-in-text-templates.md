---
title: 在文本模板中使用转义序列
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, escape sequences
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: ef3cb58c9352e81fc959dfdd2ddebd354e834fbf
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="using-escape-sequences-in-text-templates"></a>在文本模板中使用转义序列
你可以在文本模板生成文本模板标记和 （在 C# 仅在代码中） 使用转义序列转义控制字符和引号引起来。

 若要打印的输出文件的标准的代码块的打开和关闭标记，请转义标记，如下所示：

```
\<# ... \#>
```

 你可以执行相同，但有其他文本模板指令和代码块标记。

 如果文本块包括用于转义文本模板标记的字符串，你可以使用以下的转义序列：

-   如果文本模板标记前面带有转义为偶数 (\\) 字符模板分析器将包括一半的转义字符并将包含为文本模板标记序列。 例如，如果文本模板中有四个转义字符，将有两个"\\"生成文件中的字符。

-   如果文本模板标记前面带有转义为奇数 (\\) 字符，则模板分析器将包括的下半部分"\\"字符以及标记本身 (\<# 或 #>)。 标记不被视为是一个文本模板标记。

-   如果转义 (\\) 字符显示其中一个控制字符或引号 （仅在 C#) 进行转义以外的任何序列中的其他任何位置，将直接输出的字符。

## <a name="see-also"></a>请参阅

- [如何：使用转义序列基于模板生成模板](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)