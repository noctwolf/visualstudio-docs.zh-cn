---
title: "运算符 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript, operators
ms.assetid: b8602b69-aba9-46e8-86e1-cb533ad41410
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a3068a609da2468c59066ccd38f6de87cef1ed17
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="operators-javascript"></a>运算符 (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 具有各种运算符，包括算术、逻辑、按位、赋值，以及一些其他运算符。 有关说明和示例，请参阅特定运算符的相关主题。  
  
## <a name="computational-operators"></a>算术运算符  
  
|描述|符号|  
|-----------------|------------|  
|[一元求反](../javascript/reference/subtraction-operator-decrement-javascript.md)|-|  
|[递增](../javascript/reference/increment-and-decrement-operators-javascript.md)|++|  
|[递减](../javascript/reference/increment-and-decrement-operators-javascript.md)|--|  
|[乘法](../javascript/reference/multiplication-operator-decrement-javascript.md)|*|  
|[除法](../javascript/reference/division-operator-decrement-javascript.md)|/|  
|[余数算术](../javascript/reference/modulus-operator-decrementjavascript.md)|%|  
|[加法](../javascript/reference/addition-operator-decrement-javascript.md)|+|  
|[减法](../javascript/reference/subtraction-operator-decrement-javascript.md)|-|  
  
## <a name="logical-operators"></a>逻辑运算符  
  
|描述|符号|  
|-----------------|------------|  
|[逻辑“非”](../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)|!|  
|[小于](../javascript/reference/comparison-operators-javascript.md)|\<|  
|[大于](../javascript/reference/comparison-operators-javascript.md)|>|  
|[小于或等于](../javascript/reference/comparison-operators-javascript.md)|\<=|  
|[大于或等于](../javascript/reference/comparison-operators-javascript.md)|>=|  
|[相等](../javascript/reference/comparison-operators-javascript.md)|==|  
|[不相等](../javascript/reference/comparison-operators-javascript.md)|!=|  
|[逻辑“与”](../javascript/reference/logical-and-operator-decrement-javascript.md)|&&|  
|[逻辑“或”](../javascript/reference/logical-or-operator-decrement-javascript.md)|&#124;&#124;|  
|[条件（三元）](../javascript/reference/conditional-ternary-operator-decrement-javascript.md)|?:|  
|[逗号](../javascript/reference/comma-operator-decrement-javascript.md)|,|  
|[全等](../javascript/reference/comparison-operators-javascript.md)|===|  
|[不全等](../javascript/reference/comparison-operators-javascript.md)|!==|  
  
## <a name="bitwise-operators"></a>位运算符  
  
|描述|符号|  
|-----------------|------------|  
|[按位“非”](../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)|~|  
|[按位左移](../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)|<\<|  
|[按位右移](../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)|>>|  
|[无符号右移](../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)|>>>|  
|[按位“与”](../javascript/reference/bitwise-and-operator-decrement-javascript.md)|&|  
|[按位“异或”](../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)|^|  
|[按位“或”](../javascript/reference/bitwise-or-operator-decrement-javascript.md)|&#124;|  
  
## <a name="assignment-operators"></a>赋值运算符  
  
|描述|符号|  
|-----------------|------------|  
|[赋值](../javascript/reference/assignment-operator-decrement-equal-javascript.md)|=|  
|[复合赋值](../javascript/reference/compound-assignment-operators-javascript.md)|OP=（如 += 和 &=）|  
  
## <a name="miscellaneous-operators"></a>其他运算符  
  
|描述|符号|  
|-----------------|------------|  
|[delete](../javascript/reference/delete-operator-decrementjavascript.md)|删除|  
|[typeof](../javascript/reference/typeof-operator-decrementjavascript.md)|typeof|  
|[void](../javascript/reference/void-operator-decrementjavascript.md)|void|  
|[instanceof](../javascript/reference/instanceof-operator-decrementjavascript.md)|instanceof|  
|[new](../javascript/reference/new-operator-decrementjavascript.md)|new|  
|[in](../javascript/reference/in-operator-decrementjavascript.md)|中的|  
  
## <a name="equality-and-strict-equality"></a>相等和全等  
 ==（相等）和 ===（全等）之间的差异在于检查等同性之前，相等运算符将值强制转换为不同的类型。 例如，将字符串“1”与数字 1 作比较得到的结果将为 true。 另一方面，全等运算符不会强制将值转换为不同的类型，因此字符串“1”与数字1 相比得到的结果将不相等。  
  
 基元字符串、数字和布尔按值进行比较。 如果它们具有相同的值，则相等。 对象（包括 `Array`、`Function`、`String`、Number、`Boolean`、Error、`Date` 和 `RegExp` 对象）按引用进行比较。 即使这些类型的两个变量具有相同的值，但也只有在引用完全相同的对象时它们才相等。  
  
 例如:  
  
```JavaScript  
// Two strings with the same value.  
var string1 = "Hello";  
var string2 = "Hello";  
  
// Two String objects with the same value.  
var StringObject1 = new String(string1);  
var StringObject2 = new String(string2);  
  
if (string1 == string2)  
    document.write("string1 is equal to string2 <br/>");  
  
if (StringObject1 != StringObject2)  
    document.write("StringObject1 is not equal to StringObject2 <br/>");  
  
// To compare the values of String objects, use the toString() or valueOf() methods.  
if (StringObject1.valueOf() == StringObject2.valueOf())  
    document.write("The value of StringObject1 is equal to the value of StringObject2");  
  
//Output:  
// string1 is equal to string2   
// StringObject1 is not equal to StringObject2   
// The value of StringObject1 is equal to the value of StringObject2  
  
```