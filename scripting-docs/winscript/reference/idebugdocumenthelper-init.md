---
title: 'Idebugdocumenthelper:: Init |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.Init
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::Init
ms.assetid: 1dd5a01f-0779-4109-8c6c-f16f5a3835bf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4bcb64b7bbb1c61e7f031d872f7d1440fd17833
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086627"
---
# <a name="idebugdocumenthelperinit"></a>IDebugDocumentHelper::Init
`Init`方法初始化使用名称和初始属性的调试文档帮助程序。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Init(  
   IDebugApplication*  pda,  
   LPCOLESTR           pszShortName,  
   LPCOLESTR           pszLongName,  
   TEXT_DOC_ATTR       docAttr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pda`  
 [in]与此文档关联的调试应用程序。  
  
 `pszShortName`  
 [in]包含文档的短名称的以 null 结尾的字符串。  
  
 `pszLongName`  
 [in]包含文档的长名称的以 null 结尾的字符串。  
  
 `docAttr`  
 [in]指定文本文档属性。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法初始化使用名称和初始属性的调试文档帮助程序。  
  
 本文档不会显示在树中，直到`IDebugDocumentHelper::Attach`调用。  
  
## <a name="see-also"></a>请参阅  
 [Idebugdocumenthelper:: Attach](../../winscript/reference/idebugdocumenthelper-attach.md)   
 [IDebugDocumentHelper 接口](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [TEXT_DOC_ATTR 常量](../../winscript/reference/text-doc-attr-constants.md)