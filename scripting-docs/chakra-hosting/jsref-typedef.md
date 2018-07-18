---
title: JsRef Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9d4c478a45f53e83dfa59fdde21cfa4c988c92e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568527"
---
# <a name="jsref-typedef"></a>JsRef Typedef
对 Chakra 垃圾回收器所拥有的某个对象的引用。  
  
## <a name="syntax"></a>语法  
  
```  
typedef void *JsRef;  
```  
  
## <a name="remarks"></a>备注  
 只要 JsRef 引用存储在局部变量或参数中（例如堆栈上），Chakra 运行时就会自动跟踪它们。 如果将 JsRef 存储在除堆栈外的某个位置中，则需要通过调用 JsAddRef 和 JsRelease 来管理该对象的生存期，否则垃圾回收器将释放该对象，即便该对象仍处于使用中也是如此。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)