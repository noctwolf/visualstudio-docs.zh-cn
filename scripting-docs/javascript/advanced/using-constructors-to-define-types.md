---
title: "使用构造函数定义类型 | Microsoft Docs"
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
- creating objects, constructor functions
- constructor functions
- functions, constructor functions
- objects, creating [JavaScript]
- constructors, creating
ms.assetid: e869702e-4caf-4513-8dd5-fe690535f8aa
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bff42606fda27e00a537cc227a0b636e016f7c6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="using-constructors-to-define-types"></a>使用构造函数定义类型
构造函数是一个实例化特定类型的 [Object](../../javascript/objects-and-arrays-javascript.md) 的函数。 使用 new 关键字调用构造函数。 以下是包含内置 JavaScript 对象和自定义对象的构造函数的几个示例。  
  
## <a name="constructor-examples"></a>构造函数示例  
  
```JavaScript  
// Creates a generic object.  
var myObject = new Object();  
// Creates a Date object.  
var myBirthday = new Date(1961, 5, 10);  
// Creates a user defined object.  
var myCar = new Car();  
```  
  
 构造函数包含 this 关键字，它是对新创建的空对象的引用。 它通过创建属性并为其赋初始值来初始化新对象。 构造函数将返回对所构造的对象的引用。  
  
## <a name="writing-constructors"></a>编写构造函数  
 可以将 new 运算符和预定义的构造函数（如 Object()、Date() 和 Function()）一起使用来创建对象。 还可以创建定义一组属性和方法的自定义构造函数。 下面是自定义构造函数的一个示例。  
  
```JavaScript  
function Circle (xPoint, yPoint, radius) {  
    this.x = xPoint;  // The x component of the center of the circle.  
    this.y = yPoint;  // The y component of the center of the circle.  
    this.r = radius;  // The radius of the circle.  
}  
```  
  
 当你调用 Circle 构造函数时，你需要提供圆的圆心和半径的值。 最后以包含这三个属性的 Circle 对象结束。 以下是实例化 Circle 对象的方式。  
  
```JavaScript  
var aCircle = new Circle(5, 11, 99);  
```  
  
 使用自定义构造函数创建的所有对象的类型为 `object`。 JavaScript 中仅包括六种类型：`object`、`function`、`string`、`number`、`boolean` 和 `undefined`。 有关详细信息，请参阅 [typeof 运算符](../../javascript/reference/typeof-operator-decrementjavascript.md)  
  
## <a name="see-also"></a>另请参阅  
 [使用 bind 方法](../../javascript/advanced/using-the-bind-method-javascript.md)