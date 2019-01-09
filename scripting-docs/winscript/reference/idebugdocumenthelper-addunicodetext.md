---
title: 'Idebugdocumenthelper:: Addunicodetext |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddUnicodeText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddUnicodeText
ms.assetid: f4ef648e-c55d-4ef0-8df3-e808b798d3b8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 190df1f621b450c6d3b34c339d21f947f48636f2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093517"
---
# <a name="idebugdocumenthelperaddunicodetext"></a>IDebugDocumentHelper::AddUnicodeText
本文档的末尾追加一个 Unicode 字符串。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT AddUnicodeText(  
   LPCOLESTR  pszText  
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
>  如果此方法之后调用`AddDeferredText`已调用`E_FAIL`返回。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentHelper 接口](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [Idebugdocumenthelper:: Adddeferredtext](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [IDebugDocumentTextEvents 接口](../../winscript/reference/idebugdocumenttextevents-interface.md)