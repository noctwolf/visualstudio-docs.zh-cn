---
title: IDebugDocumentProvider::GetDocument |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentProvider.GetDocument
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentProvider::GetDocument
ms.assetid: da67dab0-778a-4dab-8ca3-055ee7a4f141
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: afdf039ebac10a407f8ee3b27b5918d97d7e96a9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088772"
---
# <a name="idebugdocumentprovidergetdocument"></a>IDebugDocumentProvider::GetDocument
导致要进行实例化，如果尚不存在的文档。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetDocument(  
   IDebugDocument**  ppssd  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppssd`  
 [out]调试文档的文档相对应。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法会导致如果尚不存在要实例化的文档。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentProvider 接口](../../winscript/reference/idebugdocumentprovider-interface.md)