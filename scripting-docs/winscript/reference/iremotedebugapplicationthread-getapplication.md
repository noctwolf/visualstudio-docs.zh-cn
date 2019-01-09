---
title: IRemoteDebugApplicationThread::GetApplication |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.GetApplication
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::GetApplication
ms.assetid: 9446c7f9-cfa2-408f-98c5-64f549783de1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc2e4d542619e214835d3be8354062733ebd5cb8
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091489"
---
# <a name="iremotedebugapplicationthreadgetapplication"></a>IRemoteDebugApplicationThread::GetApplication
返回与此线程关联的应用程序对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetApplication(  
   IRemoteDebugApplication**  pprda  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pprda`  
 [out]与此线程关联的应用程序对象。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回与此线程关联的应用程序对象。  
  
## <a name="see-also"></a>请参阅  
 [IRemoteDebugApplicationThread 接口](../../winscript/reference/iremotedebugapplicationthread-interface.md)