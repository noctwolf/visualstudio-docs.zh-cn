---
title: IDebugApplicationNodeEvents::onDetach |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNodeEvents.onDetach
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugApplicationNodeEvents::onDetach
ms.assetid: ef0cbe40-8c52-4bc9-bed0-9fc508abec6e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86a19a0c8ff2ce64cf524ae9b5f0ad258409f2df
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094466"
---
# <a name="idebugapplicationnodeeventsondetach"></a>IDebugApplicationNodeEvents::onDetach
处理以表明，分离调试应用程序节点对象从父节点的事件。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT onDetach();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法处理表明，分离调试应用程序节点对象从父节点的事件。  
  
 实施者`IDebugApplicationNode`接口引发此事件。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplicationNodeEvents 接口](../../winscript/reference/idebugapplicationnodeevents-interface.md)   
 [IDebugApplicationNodeEvents::onAttach](../../winscript/reference/idebugapplicationnodeevents-onattach.md)   
 [IDebugApplicationNode 接口](../../winscript/reference/idebugapplicationnode-interface.md)