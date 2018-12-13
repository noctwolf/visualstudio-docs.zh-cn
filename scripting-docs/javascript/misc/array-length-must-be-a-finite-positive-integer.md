---
title: 数组长度必须为有限正整数 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5029
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1a467040-4702-4178-848f-418a5974e907
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6589bd2e9bb4acbec5f169087a49e64417dfae7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49882556"
---
# <a name="array-length-must-be-a-finite-positive-integer"></a>数组长度必须为有限正整数
在调用**数组**不是 （全部为数字零和包含的一组正整数） 为整数的参数的构造函数。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   创建一个新时仅使用正整数`Array`对象。 如果你想要创建一个包含单个元素的不是一个整数数组，执行此操作分两步。 首先创建一个元素的数组，然后将值放在第一个元素 (array[0])。 下面是一个示例，将生成此错误。  
  
    ```JavaScript  
    var piArray = new Array(3.14159);  
    ```  
  
     下面的示例演示具有单个数字元素指定数组的正确方法。  
  
    ```JavaScript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     没有任何大小的数组，最大整数值 （大约 40 亿个） 以外的值的上限。  
  
## <a name="see-also"></a>请参阅  
 [使用数组](../../javascript/advanced/using-arrays-javascript.md)