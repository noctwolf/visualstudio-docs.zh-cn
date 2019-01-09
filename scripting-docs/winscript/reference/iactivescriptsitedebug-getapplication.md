---
title: IActiveScriptSiteDebug::GetApplication |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.GetApplication
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::GetApplication
ms.assetid: 4400f1b1-3108-4a71-b1f1-43586fe1227c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a485a7195f64754bc28d0c1905d30d6f22747c31
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090111"
---
# <a name="iactivescriptsitedebuggetapplication"></a>IActiveScriptSiteDebug::GetApplication
返回与此脚本站点关联的调试应用程序对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetApplication(  
   IDebugApplication**  ppda  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppda`  
 [out]与脚本站点关联的调试应用程序对象的指针。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_NOTIMPL`|主机不直接支持调试。|  
  
## <a name="remarks"></a>备注  
 `GetApplication`方法提供了智能主机来定义每个脚本所属的应用程序对象的方式。 脚本引擎应尝试调用此方法以获取其包含的应用程序并求助于`IProcessDebugManager::GetDefaultApplication`如果此操作失败。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptSiteDebug 接口](../../winscript/reference/iactivescriptsitedebug-interface.md)   
 [IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)