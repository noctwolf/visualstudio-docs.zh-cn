---
title: 预期] 在正则表达式 (JavaScript) |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1ca2079a-44dd-479f-a1e3-e04a14d0739e
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c49ab90dae8f30dae075906bb9c7ecb7881428f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60065072"
---
# <a name="expected--in-regular-expression-javascript"></a>正则表达式中应有“]”(JavaScript)
尝试创建字符类的正则表达式匹配项，但并未包含右方括号。 通过将它们放在方括号内，各个文本字符的组合可以组合成字符类。 字符类匹配包含任何一个字符。 例如，/ [abc] 匹配任何一个字母"a"、"b"或"c"。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
- 将右方括号添加到正则表达式。  
  
    > [!NOTE]
    >  如果您希望匹配一个方括号，对其进行转义反斜杠- \\[-这样，它不被视为特殊字符的[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]。  
  
## <a name="see-also"></a>请参阅  
 [正则表达式对象](../../javascript/reference/regular-expression-object-javascript.md)   
 [正则表达式语法 (JavaScript)](https://msdn.microsoft.com/library/1400241x)