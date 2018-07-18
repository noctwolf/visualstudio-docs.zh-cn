---
title: JsContextRef Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec1300717b59c3b901665b39ca0102988e83e853
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24567727"
---
# <a name="jscontextref-typedef"></a>JsContextRef Typedef
对脚本上下文的引用。  
  
## <a name="syntax"></a>语法  
  
```  
typedef JsRef JsContextRef;  
```  
  
## <a name="remarks"></a>备注  
 每个脚本上下文都包含自己的全局对象，它与其他脚本上下文中的全局对象不同。  
  
 许多 Chakra 托管 API 都需要一个“活动”脚本上下文，可使用 `JsSetCurrentContext` 来设置该上下文。 需要对当前上下文进行设置的 Chakra 托管 API 将在其文档中显式发现该上下文。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)