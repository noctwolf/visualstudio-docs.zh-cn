---
title: IActiveScriptErrorDebug::GetDocumentContext |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptErrorDebug.GetDocumentContext
apilocation:
- jscript.dll
helpviewer_keywords:
- IActiveScriptErrorDebug::GetDocumentContext
ms.assetid: 567601a1-551a-4905-bda1-1f54610174f4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 308ee38b6b4e2e63d113934dd535fa04ec576c2e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094219"
---
# <a name="iactivescripterrordebuggetdocumentcontext"></a>IActiveScriptErrorDebug::GetDocumentContext
此错误提供的文档上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetDocumentContext(  
   IDebugDocumentContext**  ppssc  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppssc`  
 [out]此错误的文档上下文。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 文档上下文字符位置范围应包含与错误对应的所有字符。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptErrorDebug 接口](../../winscript/reference/iactivescripterrordebug-interface.md)