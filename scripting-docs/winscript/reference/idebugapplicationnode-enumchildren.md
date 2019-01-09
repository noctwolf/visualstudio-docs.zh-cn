---
title: IDebugApplicationNode::EnumChildren |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNode.EnumChildren
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationNode::EnumChildren
ms.assetid: d79b362b-23d5-4a5e-a214-5a78618eaf71
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4967f35904a32e9b9a82426273ea7fd651a34b5a
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088122"
---
# <a name="idebugapplicationnodeenumchildren"></a>IDebugApplicationNode::EnumChildren
枚举此应用程序节点的子节点。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT EnumChildren(  
   IEnumDebugApplicationNodes**  pperddp  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pperddp`  
 [out]此节点的子节点的枚举。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法枚举此应用程序节点的子节点。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplicationNode 接口](../../winscript/reference/idebugapplicationnode-interface.md)