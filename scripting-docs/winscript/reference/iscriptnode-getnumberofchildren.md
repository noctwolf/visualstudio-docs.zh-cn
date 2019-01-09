---
title: IScriptNode::GetNumberOfChildren |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetNumberOfChildren
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetNumberOfChildren
ms.assetid: 3451c7e9-cb50-482e-9038-6e7d7ce1ecdf
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a6c1cd7ee65f4bd01373d112bc7afdcf0dd06d2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094674"
---
# <a name="iscriptnodegetnumberofchildren"></a>IScriptNode::GetNumberOfChildren
返回的子节点数目`IScriptNode`对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetNumberOfChildren(  
   ULONG              *pcsn  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pcsn`  
 [out]子节点的数目，`IScriptNode`对象具有。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [IScriptNode 接口](../../winscript/reference/iscriptnode-interface.md)