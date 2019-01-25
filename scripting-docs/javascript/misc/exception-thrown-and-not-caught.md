---
title: 引发了异常且未被捕获 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5022
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b5235490-a8e7-42e3-804e-d85235bc6f05
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 839ff08da4d26406b508a206c809b0813d2b32e1
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349031"
---
# <a name="exception-thrown-and-not-caught"></a>引发了异常且未被捕获
包含您`throw`不括在你的代码，但语句**尝试**块中，或出现没有关联**捕获**块来捕获错误。 内引发的异常**尝试**阻止使用**引发**语句，并捕获外部**重**块**捕获**语句。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   包含可以在引发异常的代码**尝试**阻止，并确保存在相应**捕获**块。  
  
-   请确保您的 catch 语句预期异常的正确格式。  
  
-   如果引发异常，请确保没有另一个相应的 catch 语句。  
  
## <a name="see-also"></a>请参阅  
 [错误对象](../../javascript/reference/error-object-javascript.md)   
 [Throw 语句](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally 语句](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)