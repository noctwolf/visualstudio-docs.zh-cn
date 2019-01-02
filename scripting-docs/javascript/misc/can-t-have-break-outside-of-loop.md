---
title: 不能有 break 位于循环外 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT1019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 11d02172-2a78-4705-a730-d21111db5f42
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce142e07a47b73778ebae6b26452806b3a036d41
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/27/2018
ms.locfileid: "53802395"
---
# <a name="cant-have-break-outside-of-loop"></a>“break”不能位于循环外
你尝试使用**中断**位于循环外的关键字。 **中断**关键字用于终止循环或`switch`语句。 它必须在循环的正文中嵌入或`switch`语句。 但是，**标签**可以按照 break 关键字。  
  
```  
break labelname;  
```  
  
 只需要的标记窗体**中断**关键字时使用嵌套循环或`switch`语句和需要中断不是最里面的循环。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   请确保**中断**关键字出现在封闭循环或 switch 语句。  
  
## <a name="see-also"></a>请参阅  
 [break 语句](../../javascript/reference/break-statement-javascript.md)   
 [控制程序流](../../javascript/controlling-program-flow-javascript.md)   
 [脚本疑难解答](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)