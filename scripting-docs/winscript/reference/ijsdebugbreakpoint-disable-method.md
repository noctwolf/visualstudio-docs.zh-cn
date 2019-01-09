---
title: 'Ijsdebugbreakpoint:: Disable 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJSDebugBreakPoint.Disable
apilocation:
- jscript9diag.dll
ms.assetid: f6f2889c-c001-4ee5-8e3f-4f36235e4fad
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 873f5d285a877e04076859b0230589ced705078b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094206"
---
# <a name="ijsdebugbreakpointdisable-method"></a>IJsDebugBreakPoint::Disable 方法
禁用断点。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Disable(void);  
```  
  
## <a name="return-value"></a>返回值  
  
## <a name="remarks"></a>备注  
 如果对已删除的断点调用，则返回 E_UNEXPECTED。 如果对已禁用的断点调用，则返回 S_FALSE。  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [IJsDebugBreakPoint 接口](../../winscript/reference/ijsdebugbreakpoint-interface.md)