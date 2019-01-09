---
title: IProcessDebugManager::RemoveApplication |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IProcessDebugManager.RemoveApplication
apilocation:
- pdm.dll
helpviewer_keywords:
- IProcessDebugManager::RemoveApplication
ms.assetid: 334e869d-81ae-4d30-9e89-89763ad4f184
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c163f756e426cab9ce36c1c8343b142bf76aafd6
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086510"
---
# <a name="iprocessdebugmanagerremoveapplication"></a>IProcessDebugManager::RemoveApplication
删除应用程序从正在运行的应用程序列表。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT RemoveApplication(  
   DWORD  dwAppCookie  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwAppCookie`  
 [in]提供的 cookie`IProcessDebugManager::AddApplication`应用程序添加到应用程序列表中时。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法删除应用程序从正在运行的应用程序列表。  
  
## <a name="see-also"></a>请参阅  
 [Iprocessdebugmanager:: Addapplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)   
 [IProcessDebugManager 接口](../../winscript/reference/iprocessdebugmanager-interface.md)