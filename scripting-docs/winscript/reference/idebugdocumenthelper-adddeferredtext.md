---
title: 'Idebugdocumenthelper:: Adddeferredtext |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddDeferredText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddDeferredText
ms.assetid: 9463cfb0-76cc-45ee-b32c-f37dce2b2e0e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba6f945e6c7fa4df83a5e301d73b3fc0bb9da92b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096078"
---
# <a name="idebugdocumenthelperadddeferredtext"></a>IDebugDocumentHelper::AddDeferredText
给定的文本可用，但它不提供字符通知帮助器。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT AddDeferredText(  
   ULONG  cChars,  
   DWORD  dwTextStartCookie  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cChars`  
 [in]若要添加的 (Unicode) 字符数。  
  
 `dwTextStartCookie`  
 [in]表示文本的起始位置的主机定义的 cookie。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_FAIL`|该方法失败。|  
  
## <a name="remarks"></a>备注  
 此方法允许主机以延迟提供要添加，直到需要它们，同时允许帮助者生成准确通知和大小信息的字符。 `dwTextStartCookie`参数是 cookie 中，定义的主机，它表示文本的起始位置。 对后续调用`IDebugDocumentText::GetText`必须提供此 cookie。 例如，表示文本在 DBCS 中的主机，在该 cookie 可能的字节偏移量。  
  
 假定调用一次`IDebugDocumentText::GetText`可以从多个调用中获取字符`AddDeferredText`。 帮助程序类可能会要求延迟字符的相同范围超过一次。  
  
> [!NOTE]
>  调用`AddDeferredText`不应通过调用混`AddUnicodeText`或`AddDBCSText`。 如果发生这种情况，`E_FAIL`返回。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentHelper 接口](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [Idebugdocumenthelper:: Addunicodetext](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)   
 [Idebugdocumenthelper:: Adddbcstext](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)