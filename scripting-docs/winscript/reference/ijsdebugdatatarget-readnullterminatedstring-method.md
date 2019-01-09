---
title: 'Ijsdebugdatatarget:: Readnullterminatedstring 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.ReadNullTerminatedString
apilocation:
- jscript9diag.dll
ms.assetid: 64683b39-6fc2-40c4-82ae-2a6f58d392d5
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a681dcedf873f0cb96f47b14278f47271cd43ec8
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093322"
---
# <a name="ijsdebugdatatargetreadnullterminatedstring-method"></a>IJsDebugDataTarget::ReadNullTerminatedString 方法
从目标读取指定的数量的字符。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT ReadNullTerminatedString(  
   UINT64 address,  
   UINT16 characterSize,  
   UINT32 maxCharacters,  
   BSTR *pString  
);  
```  
  
#### <a name="parameters"></a>参数  
 `address`  
 [in]要读取的地址。  
  
 `characterSize`  
 [in] 字符串中的每个字符的大小  
  
 `maxCharacters`  
 [in]要读取的字符数目上限。 maxCharacters 应是合理的。 大于 128 MB 的内存的任何请求将失败。  如果字符串大于 maxCharacters，结果字符串将在 maxCharacters 后被截断。  
  
 `pString`  
 [out]从目标中读取 BSTR。  
  
## <a name="return-value"></a>返回值  
  
## <a name="remarks"></a>备注  
 如果截断，则返回 S_FALSE。  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [IJsDebugDataTarget 接口](../../winscript/reference/ijsdebugdatatarget-interface.md)