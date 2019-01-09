---
title: IScriptNode::Delete |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.Delete
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::Delete
ms.assetid: 6765ff80-a9a8-40a3-a669-7fcc284c87af
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cce802cc1a6d63001cfbed020592b30a9d8dab1b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094791"
---
# <a name="iscriptnodedelete"></a>IScriptNode::Delete
删除此对象树。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Delete();  
```  
  
#### <a name="parameters"></a>参数  
 该方法采用任何参数。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 之后`Delete`调用方法时， [IScriptNode::Alive](../../winscript/reference/iscriptnode-alive.md)方法应指示该脚本节点未处于活动状态。  
  
## <a name="see-also"></a>请参阅  
 [IScriptNode 接口](../../winscript/reference/iscriptnode-interface.md)