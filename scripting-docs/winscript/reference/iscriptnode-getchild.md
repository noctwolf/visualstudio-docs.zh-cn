---
title: IScriptNode::GetChild |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetChild
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetChild
ms.assetid: 8cb3f8b0-958b-40bb-a91a-49a788661861
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 55cd6cf5233e850e4109128e322d3fc5bd0b1355
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086588"
---
# <a name="iscriptnodegetchild"></a>IScriptNode::GetChild
返回位于指定索引中的节点的子级。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetChild(  
   ULONG              isn,  
   IScriptNode        **ppsn  
);  
```  
  
#### <a name="parameters"></a>参数  
 `isn`  
 [in]子对象的父代中的索引。  
  
 `ppsn`  
 [out]一个变量来接收指向指针的地址`IScriptNode`接口的子实例。  
  
 有关`IScriptNode`表示网页的对象，此参数返回一个对象，包含一个脚本块。  
  
 有关`IScriptEntry`指定脚本块的对象，此参数返回指定的函数的对象。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 有关`IScriptEntry`指定的函数对象的对象和`IScriptScriptlet`对象，此方法失败，因为没有子条目。  
  
## <a name="see-also"></a>请参阅  
 [IScriptNode 接口](../../winscript/reference/iscriptnode-interface.md)