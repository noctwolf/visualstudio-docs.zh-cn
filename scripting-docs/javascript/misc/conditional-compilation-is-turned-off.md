---
title: 条件编译已关闭 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bcbf844ced2bb74ddfea9bd62d68877b7a3c969c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092880"
---
# <a name="conditional-compilation-is-turned-off"></a>条件编译已关闭
你尝试使用条件编译变量，但不将首次启用条件性编译上。 打开条件编译告知[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]编译器将解释为条件编译变量，开头的标识符。 为此，可开始使用该语句将条件代码：  
  
```js
/*@cc_on @*/  
```  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   将以下语句添加到条件代码的开头：  
  
    ```JavaScript  
    /*@cc_on @*/  
    ```  
  
## <a name="see-also"></a>请参阅  
 [条件编译](../../javascript/advanced/conditional-compilation-javascript.md)   
 [条件编译变量](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_on 语句](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@if 语句](../../javascript/reference/at-if-statement-javascript.md)   
 [@set 语句](../../javascript/reference/at-set-statement-javascript.md)