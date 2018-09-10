---
title: 缺少正则表达式对象 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5016
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: e226096c-c58f-4bcb-a71e-fa32ce474b67
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b8e3c48b116680fe73d4cc318038cb2c13c4164
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44280306"
---
# <a name="regular-expression-object-expected"></a>应为正则表达式对象
你尝试调用**RegExp.prototype.toString**或**RegExp.prototype.valueOf**方法以外的类型的对象上`RegExp`。 调用此类型的对象的类型必须是`RegExp`。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   仅调用**RegExp.prototype.toString**或**RegExp.prototype.valueOf**类型的对象上的方法`RegExp`。  
  
## <a name="see-also"></a>请参阅  
 [正则表达式对象](../../javascript/reference/regular-expression-object-javascript.md)   
 [正则表达式语法 (JavaScript)](https://msdn.microsoft.com/library/1400241x)