---
title: IDebugApplicationThread::SetDescription |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationThread.SetDescription
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationThread::SetDescription
ms.assetid: 084e5b74-af95-41b4-ae55-01f6f4d22168
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d1e1efc44b6e7f2a7d0bb3bf2de1a492c6793c8
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089851"
---
# <a name="idebugapplicationthreadsetdescription"></a>IDebugApplicationThread::SetDescription
设置此线程的说明。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetDescription(  
   LPCOLESTR  pstrDescription  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pstrDescription`  
 [in]此线程的说明。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法设置此线程的说明。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplicationThread 接口](../../winscript/reference/idebugapplicationthread-interface.md)