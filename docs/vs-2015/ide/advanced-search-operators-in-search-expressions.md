---
title: 搜索表达式中的高级搜索运算符 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Help Viewer 2.0, searching for keywords
- Help Viewer 2.0, searching code
- Help Viewer 2.0, searching code by programming language
- Help Viewer 2.0, searching titles
- searching code [Help Viewer 2.0]
- searching titles [Help Viewer 2.0]
ms.assetid: 0cdc1746-8481-45ec-9c53-d0d89cdcbd5e
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 24bf027f2fa480f95c0f223f8a319e7977615454
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480444"
---
# <a name="advanced-search-operators-in-search-expressions"></a>搜索表达式中的高级搜索运算符
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[搜索表达式中的高级搜索运算符](https://docs.microsoft.com/visualstudio/ide/advanced-search-operators-in-search-expressions)。  
  
通过使用高级的搜索运算符，您可以通过创建更复杂的搜索表达式较简单的优化内容搜索。 如下表所示，这些运算符可限制运行查询的上下文。  
  
> [!WARNING]
>  输入的高级搜索运算符必须以冒号结尾并且逗号前不能有空格，这样搜索引擎才能识别这些运算符。  
  
|要搜索|使用|示例|结果|  
|-------------------|---------|-------------|------------|  
|主题标题中的字词|title:|title:binaryreader|包含"binaryreader"在其标题中的主题。|  
|代码示例中的字词|code:|code:readdouble|代码示例中包含“readdouble”的的主题。|  
|特定编程语言的一个示例中的字词|code:vb:|code:vb:string|包含"string"Visual Basic 示例中的主题。|  
|与特定索引关键字关联的主题|keyword:|keyword:readbyte|与"readbyte"索引关键字关联的主题。|  
  
 可使用 code: 运算符查找任意编程语言的相关内容，但它的返回结果仅包含标记为特定编程语言的内容。 下表列出了此运算符支持的编程语言：  
  
|编程语言|使用|  
|--------------------------|---------|  
|Visual Basic|code:vb<br /><br /> 或<br /><br /> code:visualbasic|  
|C#|code:c#<br /><br /> 或<br /><br /> code:csharp|  
|C++|code:cpp<br /><br /> 或<br /><br /> code:c++<br /><br /> 或<br /><br /> code:cplusplus|  
|F#|code:f#<br /><br /> 或<br /><br /> code:fsharp|  
|JavaScript|code:javascript<br /><br /> 或<br /><br /> code:js|  
|XAML|code:xaml|  
  
## <a name="see-also"></a>请参阅  
 [搜索表达式中的逻辑运算符](../ide/logical-operators-in-search-expressions.md)   
 [全文搜索提示](../ide/full-text-search-tips.md)



