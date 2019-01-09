---
title: IEnumDebugStackFrames::Skip |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugStackFrames.Skip
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugStackFrames::Skip
ms.assetid: d893d6e9-e119-4f14-99d0-bf23dbd2d625
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 28821d90bc27d23d51db00e871807a2ccef885b7
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097508"
---
# <a name="ienumdebugstackframesskip"></a>IEnumDebugStackFrames::Skip
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
 [IEnumDebugStackFrames 接口](../../winscript/reference/ienumdebugstackframes-interface.md)