---
title: IEnumDebugApplicationNodes::Reset |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugApplicationNodes.Reset
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumDebugApplicationNodes::Reset
ms.assetid: 56ecdafe-ff11-461a-92e1-93254a49f1a1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 54595c3410bb261c9d88944dec3c198321acc715
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088655"
---
# <a name="ienumdebugapplicationnodesreset"></a>IEnumDebugApplicationNodes::Reset
将枚举序列重置到开头。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Reset();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法将枚举序列重置到开头。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugApplicationNodes 接口](../../winscript/reference/ienumdebugapplicationnodes-interface.md)