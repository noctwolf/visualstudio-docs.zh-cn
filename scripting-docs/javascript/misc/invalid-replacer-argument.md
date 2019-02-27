---
title: 无效的替换器参数 |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4727186f-facd-4aa6-9447-bbefbae83f07
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 640eefb53304de48e4ad2398a02910a1cff1b57d
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56841281"
---
# <a name="invalid-replacer-argument"></a>无效的替换器参数
尝试调用`JSON.stringify`不是有效的参数。 `replacer`参数必须为一个函数或数组。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   更改`replacer`函数或数组参数。  
  
## <a name="example"></a>示例  
 在此示例代码会导致运行时错误，因为`memberfilter`是而不是函数或数组的对象。  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Object();  
  
// This line will cause a runtime error.  
var jsontext = JSON.stringify(contact, memberfilter, "\t");  
```  
  
## <a name="see-also"></a>请参阅  
 [JSON 对象](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 函数](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript 运行时错误](../../javascript/reference/javascript-run-time-errors.md)