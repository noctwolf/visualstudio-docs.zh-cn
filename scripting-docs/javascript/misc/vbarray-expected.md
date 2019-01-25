---
title: 缺少 VBArray |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5013
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2998d7d-13a4-4bbe-b872-3ff3316551e4
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4b5416c6e37e59a60206bd21606b5214f05a269
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54347450"
---
# <a name="vbarray-expected"></a>缺少 VBArray
您提供了一个对象，不是 Visual Basic 的 safeArray，当一个期望值。  
  
```js
new VBArray(safeArray);  
```  
  
 VBArray 是只读的，不能直接创建。 SafeArray 参数是一个 VBArray 值，和之前，必须获取一个 VBArray 值传递给`VBArray`构造函数。 只有从现有的 ActiveX 或其他对象进行检索，才能获取该值。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   确保只能通过**VBArray**对象添加到**VBArray**构造函数。  
  
## <a name="see-also"></a>请参阅  
 [VBArray 对象](../../javascript/reference/vbarray-object-javascript.md)   
 [使用数组](../../javascript/advanced/using-arrays-javascript.md)