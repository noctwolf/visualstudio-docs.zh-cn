---
title: JsProjectionCallback Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 80d1c64f04f44a8560c25935fba2a48905a73260
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568247"
---
# <a name="jsprojectioncallback-typedef"></a>JsProjectionCallback Typedef
应使用正确线程中传递到 `JsProjectionEnqueueCallback` 的上下文调用 JsRT 回调。  
  
## <a name="syntax"></a>语法  
  
```  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### <a name="parameters"></a>参数  
 `jsContext`  
 需要调用 `JsSetProjectionEnqueueCallback` 以接收回调。  
  
## <a name="remarks"></a>备注  
 此 API 仅在“边缘”模式下受到支持。  
  
## <a name="requirements"></a>要求  
 jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)