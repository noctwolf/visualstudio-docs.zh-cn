---
title: 'Idebugapplication:: Setname |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.SetName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::SetName
ms.assetid: 7b0ddc58-6f20-4ce3-9bdf-81a6c1d64256
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 35f2014b25f752145766aaeb166b2ba1a766ca44
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094401"
---
# <a name="idebugapplicationsetname"></a>IDebugApplication::SetName
设置应用程序的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetName(  
   LPCOLESTR  pstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pstrName`  
 [in]应用程序的名称。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 在后续调用返回提供给此方法的名称`IRemoteDebugApplication::GetName`方法。  
  
 应在调用之前调用此方法`IProcessDebugManager::AddApplication`方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)   
 [IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)