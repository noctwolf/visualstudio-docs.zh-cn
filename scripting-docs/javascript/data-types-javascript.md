---
title: "数据类型 (JavaScript) | Microsoft Docs"
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
- Boolean data type, supported data types
ms.assetid: c7a6bd3a-4b1c-4dbe-8505-106dbf483b41
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa3a0e4cdbb25019758f89958afdf06c11f01a34
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="data-types-javascript"></a>数据类型 (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中有三种主数据类型、两种复合数据类型和两种特定数据类型。  
  
## <a name="primary-data-types"></a>主数据类型  
 主（基元）数据类型为：  
  
-   String  
  
-   数字  
  
-   Boolean  
  
## <a name="composite-data-types"></a>复合数据类型  
 复合（引用）数据类型为：  
  
-   对象  
  
-   数组  
  
## <a name="special-data-types"></a>特定数据类型  
 特定数据类型为：  
  
-   null  
  
-   未定义  
  
## <a name="string-data-type"></a>String 数据类型  
 字符串值是由零或多个 Unicode 字符（字母、数字和标点符号）组成的链表。 请使用字符串数据类型表示 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中的文本。 使用单引号或双引号将字符串文本引起来，将该字符串文本包括在脚本中。 用单引号引起的字符串中可以包含双引号，用双引号引起的字符串中也可以包含单引号。 下面是字符串的示例：  
  
```JavaScript  
"Happy am I; from care I'm free!"  
'"Avast, ye lubbers!" roared the technician.'   
"45"  
'c'  
```  
  
 请注意，[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 没有表示单个字符的类型。 要在 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中表示单个字符，可以创建仅由一个字符组成的字符串。 包含零字符 ("") 的字符串是空（零长度）字符串。  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 提供了可以包含在字符串中的转义序列，以创建不能直接键入的字符。 例如，`\t` 指定制表符。 有关详细信息，请参阅[特殊字符](../javascript/advanced/special-characters-javascript.md)。  
  
## <a name="number-data-type"></a>数字数据类型  
 在 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中，整数值和浮点值之间没有区别；[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 数字可以是两种类型中的任意一种（[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 在内部以浮点值的形式表示所有数字）。  
  
### <a name="integer-values"></a>整数值  
 整数值可以是正整数、负整数和 0。 它们可以通过以 10 为基数（十进制）、以 16 为基数（十六进制）和以 8 为基数（八进制）来表示。 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中的大部分数字都写成十进制形式。  
  
 通过在整数前面加前导“0x”（零和 x&#124;X）来表示十六进制（“hex”）整数。 十六进制整数中只能包含数字 0 - 9 和字母 A - F（大小写均可）。 字母 A 到 F 以单个数字的形式表示以 10 为基数的 10 到 15。 即，0xF 相当于 15，0x10 相当于 16。  
  
 通过在整数前面加前导“0”（零）来表示八进制整数。 八进制整数中只包含 0 - 7 的数字。 具有前导“0”并包含数字“8”和/或“9”的数字将被解释为十进制数字。  
  
 十六进制数字和八进制数字都可以是负值，但不能有小数部分，也不能写成科学（指数）计数法。  
  
> [!NOTE]
>  从 [!INCLUDE[jsv9text](../javascript/includes/jsv9text-md.md)] 开始，[parseInt 函数](../javascript/reference/parseint-function-javascript.md)不再将前缀为“0”的字符串视为八进制数值。 但在不使用 `parseInt` 函数时，前缀为“0”的字符串仍然可以被解释为八进制数值。  
  
### <a name="floating-point-values"></a>浮点值  
 浮点值可以是带有小数部分的整数。 此外，浮点值还可以用科学计数法表示。 即，使用大写或小写字母“e”来表示“10 的幂”。 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 使用数字表示形式的八字节 IEEE 754 浮点标准来表示数字。 这意味着你可以编写的最大数字为 1.79769x10<sup>308</sup>，最小数字为 5x10<sup>-324</sup>。 包含小数点且小数点前面有单个“0”的数字被解释为十进制浮点数。  
  
 注意：以“0x”或“00”开头并包含小数点的数字将生成错误。 下面是 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 数字的一些示例。  
  
|数字|描述|等效十进制数字|  
|------------|-----------------|------------------------|  
|.0001、0.0001、1e-4、1.0e-4|四个等效的浮点数字。|0.0001|  
|3.45e2|一个浮点数字。|345|  
|45|一个整数。|45|  
|0378|一个整数。 虽然此值看上去像一个八进制数字（因为以零开头），但 8 不是有效的八进制数字，因此它应被视为十进制数字。|378|  
|0377|一个八进制整数。 请注意，虽然此值看上去只比上面那个数字小 1，但它们的实际值相差甚远。|255|  
|0.0001|一个浮点数字。 即使此值以零开头，它不是八进制数字，因为它有小数点。|0.0001|  
|00.0001|此值表达错误。 两个前导零将数字标记为八进制数字，但八进制数字不能有小数部分。|N/A（编译器出错）|  
|0Xff|一个十六进制整数。|255|  
|0x37CF|一个十六进制整数。|14287|  
|0x3e7|一个十六进制整数。 请注意，这里的“e”不是幂。|999|  
|0x3.45e2|此值表达错误。 十六进制数字不能有小数部分。|N/A（编译器出错）|  
  
 此外，[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 包含具有特殊值的数字。 这些是：  
  
-   NaN（不是数字）。 对不适当的数据（比如字符串或未定义值）执行数学运算时使用该值  
  
-   正无穷大。 当一个正数大到在 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中都无法表示时，可使用该值  
  
-   负无穷大。 当一个负数小到在 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中都无法表示时，可使用该值  
  
-   正 0 和负 0。 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 区分正零和负零。  
  
## <a name="boolean-data-type"></a>boolean 数据类型  
 虽然字符串和数字数据类型实际上可以有无限多个不同的值，但布尔值数据类型只能有两个值。 它们是文本 `true` 和 `false`。 布尔值是一个真值：它指定条件是否为 true。  
  
 在脚本中进行的比较始终有一个布尔值结果。 请看以下 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 代码行。  
  
```JavaScript  
y = (x == 2000);  
```  
  
 其中，变量 `x` 的值与数字 2000 进行比较。 如果相等，则比较结果为布尔值 true，该值将赋给变量 `y`。 如果 `x` 不等于 2000，则比较结果为布尔值 `false`。  
  
 布尔值在控制结构时特别有用。 以下代码可直接将创建布尔值的比较与使用该值的语句组合。 请看以下 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 示例代码。  
  
```JavaScript  
if (x == 2000) {  
    z = z + 1;  
}  
else {  
    x = x + 1;  
}  
```  
  
 如果布尔值为 `true` (`z = z + 1`)，[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中的 `if/else` 语句执行一项操作，如果布尔值为 `false` (`x = x + 1`)，则执行另一项操作。  
  
 可将任何表达式用作比较表达式。 计算结果为 0、null、undefined 或空字符串的任何表达式都被解释为 `false`。 计算结果为任何其他值的表达式被解释为 `true`。 例如，可以使用类似下面的表达式：  
  
```JavaScript  
// This may not do what you expect. See below!  
if (x = y + z)   
```  
  
 注意：以上代码行只使用了一个等号（赋值运算符），因此不会检查 `x` 与 `y + z` 是否相等。 相反，以上代码将 `y + z` 的值赋给变量 `x`，然后检查整个表达式的结果（`x` 的值）是否为 0。 要检查 `x` 是否等于 `y + z`，需使用以下代码。  
  
```JavaScript  
// This is different from the code above!  
if (x == y + z)   
```  
  
 有关比较的详细信息，请参阅[控制程序流](../javascript/controlling-program-flow-javascript.md)。  
  
## <a name="the-null-data-type"></a>null 数据类型  
 `null` 数据类型在 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中仅具有一个值：null。 `null` 这个关键字不能用作函数或变量的名称。  
  
 包含 `null` 的变量不包含有效的数字、字符串、布尔值、数组或对象。 通过为变量赋予 `null` 值可以清除该变量的内容（不删除变量）。  
  
 注意：在 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中，`null` 与 0 不同（二者在 C 和 C++ 中等同）。 此外，请注意：[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 中的 `typeof` 运算符将 `null` 值报告为 `Object` 类型，而不是 `null` 类型。 此可能令人混淆的行为可实现向后兼容。  
  
## <a name="the-undefined-data-type"></a>undefined 数据类型  
 如果使用的对象属性不存在，或使用的是已声明但未赋值的变量，则会返回 `undefined` 值。  
  
 虽然可以通过将变量与 `undefined` 进行比较来检查变量是否存在，但也可以通过将变量类型与字符串“undefined”进行比较来检查变量类型是否为 `undefined`。 以下示例演示了如何确定是否已声明变量 `x`：  
  
```JavaScript  
  
var x;  
  
// This method works.  
if (x == undefined) {  
    document.write("comparing x to undefined <br/>");  
}  
.  
// This method doesn't work - you must check for the string "undefined".  
if (typeof(x) == undefined) {  
    document.write("comparing the type of x to undefined <br/>");  
}  
// This method does work.   
if (typeof(x) == "undefined") {  
    document.write("comparing the type of x to the string 'undefined'");  
}  
  
// Output:   
// comparing x to undefined   
// comparing the type of x to the string 'undefined'  
  
```  
  
 还可以将此未定义值与 `null` 进行比较。 如果属性 `someObject.prop` 为 `null`，或者如果属性 `someObject.prop` 不存在，则比较的结果为 `true`。  
  
```JavaScript  
someObject.prop == null;  
```  
  
 要确定对象属性是否存在，可以使用 in 运算符：  
  
```JavaScript  
if ("prop" in someObject)  
    // someObject has the property 'prop'  
```  
  
## <a name="see-also"></a>另请参阅  
 [对象和数组](../javascript/objects-and-arrays-javascript.md)   
 [typeof 运算符](../javascript/reference/typeof-operator-decrementjavascript.md)