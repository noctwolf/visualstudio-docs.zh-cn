---
title: IDebugApplicationNode::GetParent |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNode.GetParent
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationNode::GetParent
ms.assetid: 88ba3a53-0cd7-4e1f-8558-79c20ac76cc9
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 46b13c583f4e40b68610e50b37520f3d3882f364
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089643"
---
# <a name="idebugapplicationnodegetparent"></a>IDebugApplicationNode::GetParent
返回此应用程序节点的父节点。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetParent(  
   IDebugApplicationNode**  pprddp  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pprddp`  
 [out]此应用程序节点的父应用程序节点。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回此应用程序节点的父节点。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplicationNode 接口](../../winscript/reference/idebugapplicationnode-interface.md)