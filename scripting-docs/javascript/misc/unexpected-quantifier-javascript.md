---
title: 意外的限定符 (JavaScript) |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba6d34f9-2d6f-486c-a929-6cd9818be322
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 693fdf4091a6f6fdf63c701b63c4355a67ee6fbd
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096741"
---
# <a name="unexpected-quantifier-javascript"></a>意外的限定符 (JavaScript)
编写正则表达式搜索模式，创建的 pattern 元素非法的重复因子。 例如，模式  
  
```js
/^+/  
```  
  
 是非法的因为元素 ^ （输入的开头） 不能具有重复因子。 下表列出了这些元素不能具有重复因素。  
  
|元素|描述|  
|-------------|-----------------|  
|^|输入起始处|  
|$|输入结束|  
|\b|字边界|  
|\B|非字边界|  
|*|零个或多个重复项|  
|+|一个或多个重复项|  
|?|零个或一个重复项|  
|{n}|n 重复|  
|{n}|n 个或多个重复项|  
|{n，m}|从 n 到 m 次重复，非独占|  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   请确保您的搜索模式元素包含仅法律重复因素。  
  
## <a name="see-also"></a>请参阅  
 [正则表达式对象](../../javascript/reference/regular-expression-object-javascript.md)   
 [正则表达式语法 (JavaScript)](https://msdn.microsoft.com/library/1400241x)