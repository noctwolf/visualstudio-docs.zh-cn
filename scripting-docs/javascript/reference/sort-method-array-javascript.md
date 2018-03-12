---
title: "sort 方法 (Array) (JavaScript) |Microsoft 文档"
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
- sort
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Sort method
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0462e60e623b99af458beb61eb7ef4215fe8ef41
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2018
---
# <a name="sort-method-array-javascript"></a>sort 方法 (Array) (JavaScript)
排序`Array`。  
  
## <a name="syntax"></a>语法  
  
```  
  
arrayobj.sort(sortFunction)   
```  
  
## <a name="parameters"></a>参数  
 `arrayObj`  
 必须的。 任意 `Array` 对象。  
  
 `sortFunction`  
 可选。 用于确定元素的顺序的函数的名称。 如果省略，则对元素进行排序以升序，ASCII 字符。  
  
## <a name="return-value"></a>返回值  
 已排序的数组。  
  
## <a name="remarks"></a>备注  
 `sort`方法排序`Array`就地对象; 如果否新`Array`执行过程中创建对象。  
  
 `sortFunction`采用两个参数，并且必须返回下列值之一：  
  
-   负值 （小于 0） 的第一个参数传递是否小于第二个参数。  较低的索引进行排序的第一个参数。
  
-   零 (0)，如果两个自变量是等效的。  两个自变量与数组中的其他元素进行排序，但不是会彼此进行排序。
  
-   是 （大于 0） 的第一个参数是否大于第二个参数的正数值。  第二个参数进行排序的较低的索引。
  
## <a name="example"></a>示例  
 下面的示例显示如何使用 `sort` 方法。  
  
```JavaScript  
var a = new Array(4, 11, 2, 10, 3, 1);  
  
var b = a.sort();  
document.write(b);  
document.write("<br/>");  
  
// This is ASCII character order.  
// Output: 1,10,11,2,3,4)  
  
// Sort the array elements with a function that compares array elements.  
b = a.sort(CompareForSort);  
document.write(b);  
document.write("<br/>");  
// Output: 1,2,3,4,10,11.  
  
// Sorts array elements in ascending order numerically.  
function CompareForSort(first, second)  
{  
    if (first == second)  
        return 0;  
    if (first < second)  
        return -1;  
    else  
        return 1;   
}  
```  
  
## <a name="requirements"></a>惠?  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]