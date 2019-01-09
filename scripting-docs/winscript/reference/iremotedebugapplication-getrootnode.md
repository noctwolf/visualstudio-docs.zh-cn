---
title: 'Iremotedebugapplication:: Getrootnode |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.GetRootNode
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::GetRootNode
ms.assetid: 6c043aba-1dc5-41de-9711-96cde5e040f6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75b398ddac53f2633cbc090f5d49574bd4d94d36
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097768"
---
# <a name="iremotedebugapplicationgetrootnode"></a>IRemoteDebugApplication::GetRootNode
返回与该应用程序相关联的所有节点将都添加在其下的应用程序节点。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetRootNode(  
   IDebugApplicationNode**  ppdanRoot  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppdanRoot`  
 [out]调试应用程序节点将在其下添加应用程序相关的所有节点。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回与该应用程序相关联的所有节点将都添加在其下的应用程序节点。  
  
## <a name="see-also"></a>请参阅  
 [IRemoteDebugApplication 接口](../../winscript/reference/iremotedebugapplication-interface.md)