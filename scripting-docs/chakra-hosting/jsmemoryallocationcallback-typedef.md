---
title: JsMemoryAllocationCallback Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9672c23f48a2cb3e20de58012b267b30f4514d66
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568727"
---
# <a name="jsmemoryallocationcallback-typedef"></a>JsMemoryAllocationCallback Typedef
用户实现了内存分配事件的回调例程。  
  
## <a name="syntax"></a>语法  
  
```  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 callbackState  
 传递到 JsSetRuntimeMemoryAllocationCallback 的状态。  
  
 allocationEvent  
 类型分配事件的类型。  
  
 allocationSize  
 分配的大小。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 对于 JsMemoryAllocate 事件，返回 true 使运行时可继续进行分配。 若返回 false，则指示分配请求受到拒绝。 对于其他分配事件，将忽略返回值。  
  
## <a name="remarks"></a>备注  
 使用 JsSetRuntimeMemoryAllocationCallback 注册此回调。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)