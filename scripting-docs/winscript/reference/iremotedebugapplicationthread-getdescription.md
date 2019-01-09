---
title: IRemoteDebugApplicationThread::GetDescription |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.GetDescription
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::GetDescription
ms.assetid: 69842e9e-7c1c-4841-a6b2-31505fe85738
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff7e331ebd61d499ddd865409e23a5ad4ffae11a
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095428"
---
# <a name="iremotedebugapplicationthreadgetdescription"></a>IRemoteDebugApplicationThread::GetDescription
获取描述和此线程的状态。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetDescription(  
   BSTR*  pbstrDescription,  
   BSTR*  pbstrState  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrDescription`  
 [out]此线程的说明。  
  
 `pbstrState`  
 [out]线程状态的说明。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法获取的说明和此线程的状态。  
  
## <a name="see-also"></a>请参阅  
 [IRemoteDebugApplicationThread 接口](../../winscript/reference/iremotedebugapplicationthread-interface.md)