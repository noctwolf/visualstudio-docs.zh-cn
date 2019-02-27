---
title: 缺少枚举器对象 |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5015
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: dc6e32c1-a6e6-4e12-ac99-e3f65f91c8d7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14fcb4d990b03a8e7b896014403eb8dceac66b80
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56841826"
---
# <a name="enumerator-object-expected"></a>缺少枚举器对象
你尝试调用**Enumerator.prototype.atEnd、 Enumerator.prototype.item、 Enumerator.prototype.moveFirst，** 或**Enumerator.prototype.moveNext**上其他类型的对象的方法比`Enumerator`。 调用此类型的对象的类型必须是`Enumerator`。 下面是代码的一个违反此规则示例：  
  
```JavaScript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   仅调用**Enumerator.prototype.atEnd**， **Enumerator.prototype.item**， **Enumerator.prototype.moveFirst**，或**Enumerator.prototype.moveNext**类型的对象上的方法`Enumerator`。 若要查明您的对象是`Enumerator`对象，请使用：  
  
    ```js
    if(x instanceof Enumerator)  
    ```  
  
## <a name="see-also"></a>请参阅  
 [Enumerator 对象](../../javascript/reference/enumerator-object-javascript.md)