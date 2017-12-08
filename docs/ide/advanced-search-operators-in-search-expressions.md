---
redirect_url: /visualstudio/ide/logical-operators-in-search-expressions
ms.openlocfilehash: fe896af873197c95a4b226396e0b6333fdc40cfa
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
title: “搜索表达式中的高级搜索运算符 | Microsoft Docs”ms.custom: "" ms.date: "06/02/2017" ms.reviewer: "" ms.suite: "" ms.technology: 
  - "vs-help-viewer" ms.tgt_pltfrm: "" ms.topic: "article" helpviewer_keywords: 
  - “帮助查看器，搜索关键字”
  - “帮助查看器，搜索代码”
  - “帮助查看器，按编程语言搜索代码”
  - "帮助查看器，搜索标题"
  - “搜索代码 [Help Viewer]”
  - “搜索标题 [Help Viewer]”ms.assetid: 0cdc1746-8481-45ec-9c53-d0d89cdcbd5e caps.latest.revision: 9 author: "gewarren" ms.author: "gewarren" manager: ghogen
---
# <a name="advanced-search-operators-in-search-expressions"></a>搜索表达式中的高级搜索运算符
通过在帮助查看器中使用高级搜索运算符，可以指定在主题中的哪个位置查找搜索词，从而优化内容搜索。 下表介绍了四个可用的高级搜索运算符。

|要搜索|使用|示例|结果|  
|-------------------|---------|-------------|------------|  
|主题标题中的字词|title:|title:binaryreader|标题中包含“binaryreader”的主题。|  
|代码示例中的字词|code:|code:readdouble|代码示例中包含“readdouble”的的主题。|  
|特定编程语言的一个示例中的字词|code:vb:|code:vb:string|Visual Basic 代码示例中包含“string”的主题。|  
|与特定索引关键字关联的主题|keyword:|keyword:readbyte|与“readbyte”索引关键字关联的主题。|  

> [!WARNING]
>  输入的高级搜索运算符必须以冒号结尾并且逗号前不能有空格，这样搜索引擎才能识别这些运算符。    

## <a name="programming-languages-for-code-examples"></a>代码示例的编程语言
可使用 code: 运算符查找任意编程语言的相关内容，但它的返回结果仅包含标有编程语言标签的内容。 若要返回特定编程语言的示例，请使用以下编程语言值之一：  

|编程语言|搜索运算符语法|  
|--------------------|---------|  
|Visual Basic|code:vb<br/>code:visualbasic|  
|C#|code:c#<br/>code:csharp|  
|C++|code:cpp<br/>code:c++<br/>code:cplusplus|  
|F#|code:f#<br/>code:fsharp|  
|JavaScript|code:javascript<br/>code:js|  
|XAML|code:xaml|
