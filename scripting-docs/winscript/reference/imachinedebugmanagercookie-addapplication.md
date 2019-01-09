---
title: IMachineDebugManagerCookie::AddApplication |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IMachineDebugManagerCookie.AddApplication
apilocation:
- scrobj.dll
helpviewer_keywords:
- IMachineDebugManagerCookie::AddApplication
ms.assetid: 4d5503c5-aca9-4cf7-9900-f77bf5f3263d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef3dc3bddd0259eb4dd3a1fc874cbadbc16195d9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090657"
---
# <a name="imachinedebugmanagercookieaddapplication"></a>IMachineDebugManagerCookie::AddApplication
将添加到正在运行的应用程序的应用程序列表。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT AddApplication(  
   IRemoteDebugApplication*  pda,  
   DWORD                     dwDebugAppCookie,  
   DWORD*                    pdwAppCookie  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pda`  
 [in]为正在运行的应用程序的应用程序列表。  
  
 `dwDebugAppCookie`  
 [in]一个标识的调试应用程序的 cookie。  
  
 `pdwAppCookie`  
 [out]一个用于从计算机调试管理器删除应用程序的 cookie。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 进程调试管理器调用此方法时`IProcessDebugManager::AddApplication`调用。  
  
## <a name="see-also"></a>请参阅  
 [IMachineDebugManagerCookie 接口](../../winscript/reference/imachinedebugmanagercookie-interface.md)   
 [IMachineDebugManagerCookie::RemoveApplication](../../winscript/reference/imachinedebugmanagercookie-removeapplication.md)   
 [IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)