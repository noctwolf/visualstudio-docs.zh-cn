---
title: Object.getOwnPropertySymbols 函数 (JavaScript) |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 68dd69b9-5a33-44c2-ba5f-21a4ae6c0879
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cc47ae365841332f11cb02da1469a4c9fff80c3
ms.sourcegitcommit: abae48f476832f79cc2c5bac43bb1226d3fe4e48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2018
ms.locfileid: "27814955"
---
# <a name="objectgetownpropertysymbols-function-javascript"></a>Object.getOwnPropertySymbols 函数 (JavaScript)
返回对象的自有符号属性。 对象的自有符号属性是指直接在此对象上定义、而非从对象的原型继承的属性。  
  
## <a name="syntax"></a>语法  
  
```  
Object.getOwnPropertySymbols(object);  
```  
  
#### <a name="parameters"></a>参数  
 `object`  
 必须的。 包含自有符号的对象。  
  
## <a name="return-value"></a>返回值  
 包含对象的自有符号的数组。  
  
## <a name="remarks"></a>备注  
 需要使用 `Object.getOwnPropertySymbols` 来获取对象的符号属性。 `Object.getOwnPropertyNames` 不会返回符号属性。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何获取对象的符号属性。  
  
```JavaScript  
var obj = {};  
var key = Symbol('description');  
  
obj[key] = 'data';  
  
var symbols = Object.getOwnPropertySymbols(obj);  
  
console.log(symbols[0].toString());  
  
// Output:  
// undefined  
// Symbol(description)  
```  
  
## <a name="requirements"></a>惠?  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]