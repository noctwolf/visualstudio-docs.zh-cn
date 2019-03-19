---
title: IEnumDebugApplicationNodes::Skip | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugApplicationNodes.Skip
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumDebugApplicationNodes::Skip
ms.assetid: b2ad1957-95b5-4c09-9a44-5a765a5308ae
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97880e6a40efefa5f3643b474ba5d731f8dc3630
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58156991"
---
# <a name="ienumdebugapplicationnodesskip"></a>IEnumDebugApplicationNodes::Skip
将跳过枚举序列中的指定的段数。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]若要跳过枚举序列中的段的数目。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法将跳过枚举序列中的指定的段数。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugApplicationNodes 接口](../../winscript/reference/ienumdebugapplicationnodes-interface.md)