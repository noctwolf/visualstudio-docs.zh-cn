---
title: 应有 catch |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT1033
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f1cd947f-eba2-411e-8e84-8ca86f608643
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 244635605abafc5c0bd22c5203b105aa6e7dc669
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344104"
---
# <a name="expected-catch"></a>应有“catch”
使用异常处理**尝试**阻止，但没有编写关联**捕获**语句。 异常处理机制要求可能会失败，以及在发生异常时，不应执行的代码的代码将被封装在**尝试**块。 内引发的异常**尝试**阻止使用**引发**语句，并捕获外部**重**块包含一个或多个**捕获**语句。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   添加关联**捕获**块。  
  
-   请尝试使用**最后**而不是阻止**捕获**块。  
  
## <a name="see-also"></a>请参阅  
 [try...catch...最后语句](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [错误对象](../../javascript/reference/error-object-javascript.md)