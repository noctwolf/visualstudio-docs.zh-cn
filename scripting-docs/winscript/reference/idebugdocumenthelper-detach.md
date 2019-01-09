---
title: IDebugDocumentHelper::Detach |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.Detach
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::Detach
ms.assetid: 820b9a8c-9a88-479a-b095-daea99394f9c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd86e1860cf4bd22a71b6f728ca36dbd3b7414a4
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089487"
---
# <a name="idebugdocumenthelperdetach"></a>IDebugDocumentHelper::Detach
从文档树中删除此文档。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Detach();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法从文档树中删除此文档。  
  
## <a name="see-also"></a>请参阅  
 [Idebugdocumenthelper:: Attach](../../winscript/reference/idebugdocumenthelper-attach.md)   
 [IDebugDocumentHelper 接口](../../winscript/reference/idebugdocumenthelper-interface.md)