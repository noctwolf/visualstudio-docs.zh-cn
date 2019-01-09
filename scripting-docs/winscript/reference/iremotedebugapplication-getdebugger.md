---
title: IRemoteDebugApplication::GetDebugger |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.GetDebugger
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::GetDebugger
ms.assetid: 3d173b86-9281-4a3c-9550-d79408fd50ba
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ddb6ac5ab9f8597b1f8d22924bdd57204f66c359
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095441"
---
# <a name="iremotedebugapplicationgetdebugger"></a>IRemoteDebugApplication::GetDebugger
返回当前调试器连接到该应用程序。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetDebugger(  
   IApplicationDebugger**  pad  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pad`  
 [out]当前调试器连接到该应用程序。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回当前调试器连接到该应用程序。  
  
## <a name="see-also"></a>请参阅  
 [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)   
 [IRemoteDebugApplication 接口](../../winscript/reference/iremotedebugapplication-interface.md)