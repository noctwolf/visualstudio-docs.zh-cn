---
title: 'Ijsdebugdatatarget:: Readbstr 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.ReadBSTR
apilocation:
- jscript9diag.dll
ms.assetid: 4b571db7-04b9-42a0-9a3e-310ac9d0e659
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: afd216c869cd88a643f68f0abd1fc095a675e24b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095792"
---
# <a name="ijsdebugdatatargetreadbstr-method"></a>IJsDebugDataTarget::ReadBSTR 方法
从调试目标中读取 BSTR。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT ReadBSTR(  
   UINT64 address,  
   BSTR *pString  
);  
```  
  
#### <a name="parameters"></a>参数  
 `address`  
 [in]要读取的地址。  
  
 `pString`  
 [out]从调试目标读取的 BSTR。  
  
## <a name="return-value"></a>返回值  
  
## <a name="remarks"></a>备注  
 如果地址不是有效，则返回 E_JsDEBUG_INVALID_MEMORY_ADDRESS。  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [IJsDebugDataTarget 接口](../../winscript/reference/ijsdebugdatatarget-interface.md)