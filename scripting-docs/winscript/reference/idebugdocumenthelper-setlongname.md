---
title: IDebugDocumentHelper::SetLongName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.SetLongName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::SetLongName
ms.assetid: b6199e5d-9b54-43a2-9775-214b8d022607
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c16c94924459a2331a8aea41d74f561d0ecb905
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097469"
---
# <a name="idebugdocumenthelpersetlongname"></a>IDebugDocumentHelper::SetLongName
设置文档的长名称。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetLongName(  
   LPCOLESTR  pszLongName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszLongName`  
 [in]包含文档的长名称的以 null 结尾的字符串。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法设置文档的一个新的长名称。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentHelper 接口](../../winscript/reference/idebugdocumenthelper-interface.md)