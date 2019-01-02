---
title: 预期 ' @' |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT1032
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 82ff8b74-1710-4358-9a26-dc92ab29c53b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 191402a9ba265e5acfb15d1931e260f6b366687e
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804547"
---
# <a name="expected-"></a>应有“@”
尝试创建一个变量以与使用的条件编译语句一起使用`@set`语句，但是没有按照 at 符号"**@**"的变量名称之前。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   添加 at 符号"**@**"变量名称之前。 例如：  
  
    ```JavaScript  
    @set @myvar = 1  
    ```  
  
## <a name="see-also"></a>请参阅  
 [@set 语句](../../javascript/reference/at-set-statement-javascript.md)   
 [条件编译](../../javascript/advanced/conditional-compilation-javascript.md)   
 [条件编译变量](../../javascript/advanced/conditional-compilation-variables-javascript.md)