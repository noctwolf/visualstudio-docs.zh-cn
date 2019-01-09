---
title: 'Ijsenumdebugproperty:: Next 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsEnumDebugProperty.Next
apilocation:
- jscript9diag.dll
ms.assetid: 9fad1893-483a-440c-88c1-469494212300
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e6b0e3499f9420d42660880f616d2d0873d7a0f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086770"
---
# <a name="ijsenumdebugpropertynext-method"></a>IJsEnumDebugProperty::Next 方法
读取此对象的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Next(  
   ULONG count,  
   IJsDebugProperty **ppDebugProperty,  
   ULONG *pActualCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `count`  
 [in]要读取的属性数。  
  
 `ppDebugProperty`  
 [out]表示属性浏览器的对象。  
  
 `pActualCount`  
 [out]对象的属性的实际数目。  
  
## <a name="return-value"></a>返回值  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [IJsEnumDebugProperty 接口](../../winscript/reference/ijsenumdebugproperty-interface.md)