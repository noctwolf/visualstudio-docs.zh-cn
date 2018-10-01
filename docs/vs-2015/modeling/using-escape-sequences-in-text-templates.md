---
title: 在文本模板中使用转义序列 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, escape sequences
ms.assetid: 36fff542-2f42-460f-a2d5-03fc76817f3b
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 24e2629001d7c426193059175eab64ea0ab8dacf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477153"
---
# <a name="using-escape-sequences-in-text-templates"></a>在文本模板中使用转义序列
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[在文本模板中使用转义序列](https://docs.microsoft.com/visualstudio/modeling/using-escape-sequences-in-text-templates)。  
  
在文本模板生成文本模板标记并 （在 C# 仅代码），可以使用转义序列转义控制字符和引号引起来。  
  
 若要打印的标准代码块的输出文件的打开和关闭标记，请按如下所示转义标记：  
  
```  
\<# ... \#>  
```  
  
 您也可以执行同样的其他文本模板指令和代码块标记。  
  
 如果文本块包括用于转义文本模板标记的字符串，则可能会使用以下的转义序列：  
  
-   如果文本模板标记前面有偶数个转义 (\\) 字符在模板分析器将包括半转义字符，包括为文本模板标记序列。 例如，如果文本模板中有四个转义符，将有两个"\\"生成文件中的字符。  
  
-   如果文本模板标记前面有奇数数目的转义 (\\) 字符，在模板分析器将包括的下半部分"\\"字符以及标记本身 (\<# >)。 标记不被认为是一个文本模板标记。  
  
-   如果转义符 (\\) 字符将出现在其中将转义的控制字符或引号 （在仅限 C#) 之外的任何序列中的其他任何位置，将直接输出的字符。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用转义序列基于模板生成模板](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)



