---
title: 未终止注释 |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1016
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d4286315-814b-4966-b4c4-1ee19d796eff
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2b21c585bb48b55929a78554d686477e0fa5649
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56842437"
---
# <a name="unterminated-comment"></a>未终止的注释
开始的多行注释块，但未正确终止它。 多行注释开头"/ *"的组合，并最终以反"\*/"组合。 下面是一个示例：  
  
```JavaScript  
/* This is a comment  
This is another part of the same comment.*/  
```  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   一定要终止多行注释以"* /"。  
  
## <a name="see-also"></a>请参阅  
 [Comment 语句](../../javascript/reference/comment-statements-javascript.md)