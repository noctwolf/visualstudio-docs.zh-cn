---
title: IDebugDocumentHelper::GetScriptBlockInfo |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.GetScriptBlockInfo
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::GetScriptBlockInfo
ms.assetid: 332d7540-bbbe-4747-95ec-e47384d4f4e6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd12aff51c661c2ba5af9ef909bfa481d22101d6
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095285"
---
# <a name="idebugdocumenthelpergetscriptblockinfo"></a>IDebugDocumentHelper::GetScriptBlockInfo
检索一的系列字符和对应的脚本块的脚本引擎。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetScriptBlockInfo(  
   DWORD_PTR        dwSourceContext,  
   IActiveScript**  ppasd,  
   ULONG*           piCharPos,  
   ULONG*           pcChars  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwSourceContext`  
 [in]脚本块的源上下文。  
  
 `ppasd`  
 [out]此脚本块的脚本引擎。  
  
 `piCharPos`  
 [out]脚本块的开始位置。  
  
 `cChars`  
 [out]脚本块中的字符数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法检索一的系列字符和对应的脚本块的脚本引擎。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentHelper 接口](../../winscript/reference/idebugdocumenthelper-interface.md)