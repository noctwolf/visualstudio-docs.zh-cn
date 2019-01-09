---
title: IDebugApplicationNodeEvents::onAddChild |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNodeEvents.onAddChild
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugApplicationNodeEvents::onAddChild
ms.assetid: 59ce33cf-1843-4b03-98a2-34859d3023f7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a211989202c0d5b5c0d6c99fe2d6fbb00978787
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088681"
---
# <a name="idebugapplicationnodeeventsonaddchild"></a>IDebugApplicationNodeEvents::onAddChild
处理事件时的子节点添加到调试应用程序节点对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT onAddChild(  
   IDebugApplicationNode*  prddpChild  
);  
```  
  
#### <a name="parameters"></a>参数  
 `prddpChild`  
 [in]已添加的子调试应用程序节点。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法可处理事件时的子节点添加到调试应用程序节点对象。  
  
 实施者`IDebugApplicationNode`接口引发此事件  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplicationNodeEvents 接口](../../winscript/reference/idebugapplicationnodeevents-interface.md)   
 [IDebugApplicationNodeEvents::onRemoveChild](../../winscript/reference/idebugapplicationnodeevents-onremovechild.md)   
 [IDebugApplicationNode 接口](../../winscript/reference/idebugapplicationnode-interface.md)