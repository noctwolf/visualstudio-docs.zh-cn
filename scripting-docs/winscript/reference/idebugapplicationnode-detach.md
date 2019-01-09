---
title: IDebugApplicationNode::Detach |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNode.Detach
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationNode::Detach
ms.assetid: 36bb3e54-a4df-48d5-a6de-3b8d4c0e98a8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec67c17b184000239cd60dbf138a91fda8209c26
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086992"
---
# <a name="idebugapplicationnodedetach"></a>IDebugApplicationNode::Detach
从项目树中删除此应用程序节点。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Detach();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法从项目树中删除此应用程序节点。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplicationNode::Attach](../../winscript/reference/idebugapplicationnode-attach.md)   
 [IDebugApplicationNode 接口](../../winscript/reference/idebugapplicationnode-interface.md)