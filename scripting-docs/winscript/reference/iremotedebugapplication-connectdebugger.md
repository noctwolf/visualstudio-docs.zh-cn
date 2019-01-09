---
title: IRemoteDebugApplication::ConnectDebugger |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.ConnectDebugger
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::ConnectDebugger
ms.assetid: ded94101-7efe-466f-aa70-b3e30a38c4d8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e6db85ab30d04ebaf24ec0e955aab529ff8799d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088850"
---
# <a name="iremotedebugapplicationconnectdebugger"></a>IRemoteDebugApplication::ConnectDebugger
将调试器连接到此应用程序。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT ConnectDebugger(  
   IApplicationDebugger*  pad  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pad`  
 [in]使调试器附加到此应用程序。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_FAIL`|调试器已连接到此应用程序。|  
  
## <a name="remarks"></a>备注  
 应用程序可以具有一次连接只能有一个调试器。 如果调试器已连接，此方法将失败。  
  
## <a name="see-also"></a>请参阅  
 [IRemoteDebugApplication::GetDebugger](../../winscript/reference/iremotedebugapplication-getdebugger.md)   
 [IRemoteDebugApplication 接口](../../winscript/reference/iremotedebugapplication-interface.md)