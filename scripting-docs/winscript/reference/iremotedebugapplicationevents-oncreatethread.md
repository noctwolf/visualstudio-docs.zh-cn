---
title: IRemoteDebugApplicationEvents::OnCreateThread |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEvents.OnCreateThread
apilocation:
- jscript.dll
helpviewer_keywords:
- IRemoteDebugApplicationEvents::OnCreateThread
ms.assetid: 0b7c5181-eda6-4303-b4ae-d45962e8a3d3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3ff45733723395dc80d85c6c3242f24ba1474060
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088915"
---
# <a name="iremotedebugapplicationeventsoncreatethread"></a>IRemoteDebugApplicationEvents::OnCreateThread
处理在创建线程事件。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT OnCreateThread(  
   IRemoteDebugApplicationThread*  prdat  
);  
```  
  
#### <a name="parameters"></a>参数  
 `prdat`  
 [in]新创建的线程。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法可处理在创建线程事件。  
  
## <a name="see-also"></a>请参阅  
 [IRemoteDebugApplicationEvents 接口](../../winscript/reference/iremotedebugapplicationevents-interface.md)