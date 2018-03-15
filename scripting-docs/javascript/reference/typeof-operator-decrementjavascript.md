---
title: "typeof 运算符 (JavaScript) |Microsoft 文档"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- typeof_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- typeof operator
ms.assetid: ee8a1036-119f-486f-b034-b07bdba87f0c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9ff8c7942c773d138dd599956c41d1e583e6288
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="typeof-operator-javascript"></a>typeof 运算符 (JavaScript)
返回标识表达式数据类型的字符串。  
  
## <a name="syntax"></a>语法  
  
```  
  
typeof[(]expression[)] ;  
```  
  
## <a name="remarks"></a>备注  
 *表达式*自变量是为哪种类型查找信息任何表达式。  
  
 `typeof`运算符将类型信息作为字符串返回。 有七个可能的值`typeof`返回:"数字，""string，""布尔值"、"对象，""函数，""未定义，"和"未知"。  
  
 参数是可选的则括号`typeof`语法。  

 对象可能返回作为 XMLHTTPRequest 中的未知类型。 在 JavaScript 中不支持模拟 COM 对象可能还返回作为未知类型。
  
## <a name="example"></a>示例  
 下面的示例测试变量的数据类型。  
  
```JavaScript  
var index = 5;  
var result = (typeof index === 'number');  
// Output: true  
  
var description = "abc";  
var result = (typeof description === 'string');  
// Output: true  
```  
  
## <a name="example"></a>示例  
 下面的示例为数据类型的测试`undefined`声明和未声明的变量。  
  
```JavaScript  
var declared;  
var result = (declared === undefined);  
// Output: true  
  
var result = (typeof declared === 'undefined');  
// Output: true  
  
var result = (typeof notDeclared === 'undefined')  
// Output: true  
  
var obj = {};  
var result = (typeof obj.propNotDeclared === 'undefined');  
// Output: true  
  
// An undeclared variable cannot be used in a comparison without  
// the typeof operator, so the next line generates an error.  
//  var result = (notDeclared === undefined);  
```  
  
## <a name="requirements"></a>惠?  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Array.isArray 函数](../../javascript/reference/array-isarray-function-javascript.md)   
 [Object.getPrototypeOf Function](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [undefined 的常量](../../javascript/reference/undefined-constant-javascript.md)   
 [比较运算符](../../javascript/reference/comparison-operators-javascript.md)   
 [数据类型](../../javascript/data-types-javascript.md)   
 [运算符优先级](../../javascript/operator-subtractprecedence-javascript.md)   
 [运算符摘要 (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)