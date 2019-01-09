---
title: 无法给函数结果赋值 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5003
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ee8ffb3a-1451-4cb3-99bf-5e9cf8b77d79
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a29c3f20392dc216c0306137c0dec6b22aaa58a
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093855"
---
# <a name="cannot-assign-to-a-function-result"></a>无法给函数结果赋值
你试图将值分配给函数结果。 可以将函数的结果赋给一个变量，但不能用作变量。 如果你想要将新值分配给该函数本身，则省略括号 （函数调用运算符）。 下面的示例演示的情况下，会生成此错误。  
  
```js
myFunction() = 42;  // Attempting to assign the value 42 to the result of the function call.  
```  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   不使用函数调用结果的值用作可以*将分配给*。 您可以将函数调用的结果的分配*给一个变量*尽管。  
  
    ```JavaScript  
    myVar = myFunction(42);  
    ```  
  
-   或者，可以将该函数本身 （而不是其返回值） 分配给一个变量。  
  
    ```JavaScript  
    myFunction = new Function("return 42;");  
    ```  
  
## <a name="see-also"></a>请参阅  
 [函数对象](../../javascript/reference/function-object-javascript.md)   
 [编写 JavaScript 代码](../../javascript/writing-javascript-code.md)   
 [函数](../../javascript/functions-javascript.md)