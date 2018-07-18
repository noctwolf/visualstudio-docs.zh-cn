---
title: JsMemoryEventType 枚举 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef39008ba84337cebdc9613db17cc9fbdfc8aa79
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568517"
---
# <a name="jsmemoryeventtype-enumeration"></a>JsMemoryEventType 枚举
分配回调事件类型。  
  
## <a name="syntax"></a>语法  
  
```  
enum JsMemoryEventType;  
```  
  
## <a name="members"></a>成员  
  
### <a name="values"></a>值  
  
|名称|描述|  
|----------|-----------------|  
|`JsMemoryAllocate`|指示内存分配请求。|  
|`JsMemoryFailure`|指示失败的分配事件。|  
|`JsMemoryFree`|指示内存释放事件。|  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)