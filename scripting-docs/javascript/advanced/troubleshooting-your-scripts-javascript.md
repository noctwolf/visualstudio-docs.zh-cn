---
title: "脚本疑难解答 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- automative type conversion
- troubleshooting scripts
ms.assetid: 0e0545d9-44e5-4179-befc-99a882c5c672
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e0193e6dc0996d5e2d0d3df7103c7705d29477
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="troubleshooting-your-scripts-javascript"></a>脚本疑难解答 (JavaScript)
任何编程语言都有其自身特点。 例如，[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 中 `null` 值的用法就与 C 或 C++ 语言中 `Null` 值的用法不同。  
  
 以下是编写 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 脚本时可能会遇到的问题和需注意的一些事项。  
  
## <a name="syntax-errors"></a>语法错误  
 编写脚本时务必注意细节。 例如，字符串必须使用引号括起来。  
  
## <a name="order-of-script-interpretation"></a>脚本解释的顺序  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 解释是 Web 浏览器 HTML 分析过程的一部分。 如果在文档中将脚本放在 \<HEAD> 标记中，系统会先于 \<BODY> 标记中的所有内容解释该脚本。 如果在 \<BODY> 标记中创建了对象，在分析 \<HEAD> 时这些对象并不存在，因此脚本无法操作这些对象。  
  
> [!NOTE]
>  此行为是 Internet Explorer 所特有的。 ASP 和 WSH 的执行模型与此不同（与其他主机一样）。  
  
## <a name="automatic-type-coercion"></a>自动类型强制转换  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 是一种松散类型的语言，具有自动强制转换的特点。 即使不同类型的值不相等，下面示例中表达式的计算结果也为 true。  
  
```JavaScript  
"100" == 100;  
false == 0;  
```  
  
 要检查类型和值是否均相同，请使用严格相等运算符 (===)。 以下两者的计算结果均为 false：  
  
```JavaScript  
"100" === 100;  
false === 0;  
```  
  
## <a name="operator-precedence"></a>运算符优先级  
 [运算符优先级](../../javascript/operator-subtractprecedence-javascript.md)确定在对表达式求值的过程中何时执行计算。 在下面的示例中，系统会先于减法运算执行乘法运算，即使表达式中减法运算出现在前。  
  
```JavaScript  
theRadius = aPerimeterPoint - theCenterpoint * theCorrectionFactor;  
```  
  
## <a name="using-forin-loops-with-objects"></a>对对象使用 for...in 循环  
 使用 [for...in](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) 循环循环访问对象的属性时，无法预测或控制按何种顺序将对象的字段分配给循环计数器变量。 并且，该顺序在不同的语言实现中可能会不同。  
  
## <a name="with-keyword"></a>with 关键字  
 使用 [with](../../javascript/reference/with-statement-javascript.md) 语句可以非常方便地访问指定对象中已存在的属性，但不能向对象添加属性。 要在对象中创建新的属性，必须专门引用该对象。  
  
## <a name="this-keyword"></a>this 关键字  
 可以在对象定义内使用 `this` 关键字来引用对象本身，但是当函数不是对象定义时，不能使用 `this` 或类似关键字来引用当前正在执行的函数。 如果函数作为方法分配给对象，则可在函数内使用 `this` 关键字引用该对象。  
  
## <a name="writing-a-script-that-writes-a-script-in-internet-explorer"></a>编写在 Internet Explorer 中编写脚本的脚本  
 解释器遇到 \</SCRIPT> 标记时，该标记会终止当前脚本。 要显示“\</SCRIPT>”本身，请将其至少重写为两个字符串，例如“\</SCR”和“IPT>”，之后可在写出这两个字符串的语句中将这两个字符串连接起来。  
  
## <a name="implicit-window-references-in-internet-explorer"></a>Internet Explorer 中的隐式窗口引用  
 由于一次可以打开多个窗口，隐式窗口引用指向当前窗口。 对于其他窗口，必须使用显式引用。