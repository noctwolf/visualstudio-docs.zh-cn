---
title: 'Ijsdebugframe:: Getdocumentpositionwithid 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetDocumentPositionWithId
apilocation:
- jscript9diag.dll
ms.assetid: 48f8eb26-8ae4-4d5c-bd94-796023b03bcb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c37f31ca6b75ca826dbdab93847a1e70ff054c1
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090007"
---
# <a name="ijsdebugframegetdocumentpositionwithid-method"></a>IJsDebugFrame::GetDocumentPositionWithId 方法
返回此堆栈帧的用户级别文档中的当前位置。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetDocumentPositionWithId(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pDocumentId`  
 [out]源文档 （指向 idebugdocumenttext 的指针） 的唯一 ID。  
  
 `pCharacterOffset`  
 [out]从脚本开始处的从零开始的字符偏移量。  
  
 `pStatementCharCount`  
 [out]当前语句开始处的长度 * pCharacterOffset，以字符为单位。  
  
## <a name="return-value"></a>返回值  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [IJsDebugFrame 接口](../../winscript/reference/ijsdebugframe-interface.md)