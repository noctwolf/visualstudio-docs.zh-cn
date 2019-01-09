---
title: IEnumRemoteDebugApplicationThreads::Clone |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumRemoteDebugApplicationThreads.Clone
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumRemoteDebugApplicationThreads::Clone
ms.assetid: d016e7cf-ae73-48ff-aee7-810222e0b05c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e64a83b9cf5184e8a7dfe45cc33b698e5bbdd4f6
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091689"
---
# <a name="ienumremotedebugapplicationthreadsclone"></a>IEnumRemoteDebugApplicationThreads::Clone
创建一个包含与当前枚举数相同的状态的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Clone(  
   IEnumRemoteDebugApplicationThreads**  pperdat  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pperdat`  
 [out]返回`IEnumRemoteDebugApplicationThreads`接口的枚举器的克隆。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法创建一个包含与当前枚举数相同的状态的枚举器。  
  
## <a name="see-also"></a>请参阅  
 [IEnumRemoteDebugApplicationThreads 接口](../../winscript/reference/ienumremotedebugapplicationthreads-interface.md)