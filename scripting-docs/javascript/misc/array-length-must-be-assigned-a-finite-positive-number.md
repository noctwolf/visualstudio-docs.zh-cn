---
title: 数组长度必须赋值为有限正数 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63a9d714173334192028b9096de41968befa85ef
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49825499"
---
# <a name="array-length-must-be-assigned-a-finite-positive-number"></a>数组长度必须赋值为有限正数
设置时**长度**属性的现有**数组**对象，指定不是正数值或零的数组长度。 此错误发生时将值赋给**长度**的属性`Array`对象，它为负或不是数字 (`NaN`)。 请注意，[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]自动将小数数字转换为整数。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   将一个正整数分配给 length 属性。 没有任何大小的数组，最大整数值 （大约 40 亿个） 以外的值的上限。 下面的示例演示设置的正确方式**长度**的属性**数组**对象。  
  
    ```JavaScript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## <a name="see-also"></a>请参阅  
 [使用数组](../../javascript/advanced/using-arrays-javascript.md)