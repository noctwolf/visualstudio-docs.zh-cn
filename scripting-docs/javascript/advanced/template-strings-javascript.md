---
title: 模板字符串 (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2e525a5-b0fc-49c3-95a0-641788e5c12a
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7b6aa430fd4f958c5519093b85d399060b6031a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24569147"
---
# <a name="template-strings-javascript"></a>模板字符串 (JavaScript)
在 [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)] 中，可以使用模板字符串来构造具有嵌入式表达式的字符串文本。 模板字符串还为多行字符串提供内置支持。  
  
 若要构造模板字符串，请使用重读符号（也称为反引号）(') 替代单引号或双引号括起字符串。 下面的代码示例演示一个简单的模板字符串。  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 模板字符串可以在无需使用换行符 (\n) 的情况下包含换行。  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 $ 字符用于指定模板字符串内的占位符。 语法是 ${expression}，其中 expression 是任意 JavaScript 表达式（如变量或函数），如以下示例中所示。  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 带标记的模板函数，它可以通过使用由模板字符串中自变量调用的函数来修改此模板字符串的值。 第一个实参是字符串文本的数组，由内含的模板字符串表达式分隔；第二个实参是包含模板字符串表达式的值的数组（[Rest 形参](../../javascript/functions-javascript.md)）。  
  
 在以下示例中，带标记的模板函数 buildURL 用于构造 URL。 此语法要使用后面紧跟模板字符串的函数名。  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 如果需要访问传入的原始字符串值，则传递给带标记的模板函数的第一个参数支持可返回传入字符串的原始字符串形式的 `raw` 属性。  
  
```  
function buildURL(strArray, ...valArray) {  
    console.log(strArray.raw);  
}  
  
var lang = "en-us";  
var a = "library";  
var b = "dn771551.aspx";  
  
// Call the tagged template function.  
var url = buildURL`http://msdn.microsoft.com/${lang}/${a}/${b}`;  
  
// Ouput:  
// http://msdn.microsoft.com/  
// /  
// en-us  
// library  
```  
  
> [!NOTE]
>  还可使用 [String.raw](../../javascript/reference/string-raw-function-javascript.md) 函数返回模板字符串的原始字符串形式。  
  
## <a name="see-also"></a>另请参阅  
 [JavaScript 语言参考](../../javascript/javascript-language-reference.md)   
 [高级 JavaScript](../../javascript/advanced/advanced-javascript.md)