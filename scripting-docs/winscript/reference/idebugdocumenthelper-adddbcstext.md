---
title: 'Idebugdocumenthelper:: Adddbcstext |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddDBCSText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddDBCSText
ms.assetid: 5e5011b2-bbb4-491b-9a11-eb2846be44aa
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86d4ac5cb7371f35edb84a44159e589c898bfa3d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090384"
---
# <a name="idebugdocumenthelperadddbcstext"></a>IDebugDocumentHelper::AddDBCSText
本文档的末尾追加一个 DBCS 的字符串。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT AddDBCSText(  
   LPCSTR  pszText  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszText`  
 [in]指向以 null 结尾的字符串包含文本指针。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_FAIL`|该方法不能添加字符。|  
  
## <a name="remarks"></a>备注  
 此方法将生成`IDebugDocumentTextEvents`通知。  
  
> [!NOTE]
>  如果此方法之后调用`IDebugDocumentHelper::AddDeferredText`已调用`E_FAIL`返回。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentHelper 接口](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [Idebugdocumenthelper:: Adddeferredtext](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [IDebugDocumentTextEvents 接口](../../winscript/reference/idebugdocumenttextevents-interface.md)