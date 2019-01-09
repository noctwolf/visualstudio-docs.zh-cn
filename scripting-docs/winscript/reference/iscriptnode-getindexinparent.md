---
title: IScriptNode::GetIndexInParent |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetIndexInParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetIndexInParent
ms.assetid: 521c1ca1-2d27-4344-bf3b-d8b53132b648
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c484d212e2dccf20717aec5dca44d5c3319e15c9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089565"
---
# <a name="iscriptnodegetindexinparent"></a>IScriptNode::GetIndexInParent
返回父级的子列表中的对象的索引。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetIndexInParent(  
   ULONG              pisn,  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pisn`  
 [out]返回父级的子列表中的对象的索引。  
  
 如果调用此方法`IScriptNode`对象，表示一个 Web 页面时，此参数将返回 0。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [IScriptNode 接口](../../winscript/reference/iscriptnode-interface.md)