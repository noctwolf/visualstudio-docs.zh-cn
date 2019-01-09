---
title: IDebugHelper::CreateSimpleConnectionPoint |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugHelper.CreateSimpleConnectionPoint
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugHelper::CreateSimpleConnectionPoint
ms.assetid: 5e4798ce-6f9f-4184-9853-67bf8c8524ab
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b478f425b1aaf284bc7af744f5ac99f9be7fe8c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097066"
---
# <a name="idebughelpercreatesimpleconnectionpoint"></a>IDebugHelper::CreateSimpleConnectionPoint
返回包装的事件接口给定`IDispatch`对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT CreateSimpleConnectionPoint(  
   IDispatch*                pdisp  
   ISimpleConnectionPoint**  ppscp  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdisp`  
 [in]`IDispatch`对象包装。  
  
 `ppscp`  
 [out]包装的事件接口`pdisp`。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 返回包装的事件接口给定`IDispatch`(请参阅[ISimpleConnectionPoint 接口](../../winscript/reference/isimpleconnectionpoint-interface.md))。  
  
## <a name="see-also"></a>请参阅  
 [IDebugHelper 接口](../../winscript/reference/idebughelper-interface.md)   
 [ISimpleConnectionPoint 接口](../../winscript/reference/isimpleconnectionpoint-interface.md)