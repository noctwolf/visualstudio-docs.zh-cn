---
title: '&#39;返回&#39;语句在函数外的 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07b633c87dc11b291a5a5783f8121b2a368996d6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49846509"
---
# <a name="39return39-statement-outside-of-function"></a>&#39;返回&#39;语句在函数外
您使用`return`全局作用域中的代码的语句。 `return`语句应仅出现在函数体。  
  
 调用的函数`()`运算符是一个表达式。 所有表达式都具有值;`return`语句用于指定函数所返回的值。 常规形式为：  
  
```  
  
return [ expression ];  
```  
  
 当`return`执行语句时，*表达式*是评估并作为函数值返回。 如果没有任何表达式**未定义**返回。  
  
 函数的执行停止时`return`即使还有其他语句仍在函数体中执行语句。 此规则的例外是如果**返回**语句出现在**尝试**块中，且相应**最后**阻止，请在代码**最后**块将执行该函数返回之前。  
  
 如果函数返回，因为无需执行到达函数体的终点`return`语句，返回的值是**未定义**值 （这就意味着函数结果不能用作较大表达式的一部分).  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   删除`return`语句从你的代码 （全局范围） 的主要部分。  
  
## <a name="see-also"></a>请参阅  
 [return 语句](../../javascript/reference/return-statement-javascript.md)   
 [函数对象](../../javascript/reference/function-object-javascript.md)   
 [caller 属性 (Function)](../../javascript/reference/caller-property-function-javascript.md)