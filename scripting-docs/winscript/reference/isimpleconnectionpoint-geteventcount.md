---
title: ISimpleConnectionPoint::GetEventCount |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.GetEventCount
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::GetEventCount
ms.assetid: f1527d5b-6076-4536-8e59-e55da741ef39
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce53089b3dc468043648378d80e54cc2d3188358
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089799"
---
# <a name="isimpleconnectionpointgeteventcount"></a>ISimpleConnectionPoint::GetEventCount
返回此接口上公开的事件数。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetEventCount(  
   ULONG*  pulCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pulCount`  
 [out]在此界面计数上公开的事件数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回此接口上公开的事件的数。  
  
## <a name="see-also"></a>请参阅  
 [ISimpleConnectionPoint 接口](../../winscript/reference/isimpleconnectionpoint-interface.md)