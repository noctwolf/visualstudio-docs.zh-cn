---
title: IRemoteDebugApplicationEx:GetHostPid |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:GetHostPid
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:GetHostPid
ms.assetid: 4cf9f46c-29cf-4201-87f0-5b1ddbed2f2b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7570abb8436a49fb80f548d1a7136bf0fe7e0814
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091450"
---
# <a name="iremotedebugapplicationexgethostpid"></a>IRemoteDebugApplicationEx:GetHostPid
返回主机应用程序的进程 ID。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetHostPid(  
   DWORD*  dwHostPid  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwHostPid`  
 [out]主机进程标识符。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 由 IDE。  
  
## <a name="see-also"></a>请参阅  
 [IRemoteDebugApplicationEx 接口](http://msdn.microsoft.com/en-us/2f65fa67-06b7-4053-8945-22383ab66343)