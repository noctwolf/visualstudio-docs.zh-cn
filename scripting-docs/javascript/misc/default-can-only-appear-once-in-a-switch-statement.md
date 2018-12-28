---
title: default 只能出现一次在 switch 语句 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT1027
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a94100f4-6ee5-4759-b635-9d309e47111e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4f254825e27793999932b772ac4bc2512908fae
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/27/2018
ms.locfileid: "53803878"
---
# <a name="default-can-only-appear-once-in-a-switch-statement"></a>“default”在“switch”语句中只能出现一次
你尝试使用**默认**多次 switch 语句内的语句。 默认情况下始终是 switch 语句 （它是 fall-through 事例） 中的最后一个 case 语句。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   删除任何额外**默认**case 语句从你`switch`语句 （在大多数一个默认 case 语句，在 switch 语句中使用）。  
  
## <a name="see-also"></a>请参阅  
 [switch 语句](../../javascript/reference/switch-statement-javascript.md)   
 [控制程序流](../../javascript/controlling-program-flow-javascript.md)   
 [JavaScript 保留字](../../javascript/reference/javascript-reserved-words.md)