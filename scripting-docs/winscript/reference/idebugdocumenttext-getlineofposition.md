---
title: IDebugDocumentText::GetLineOfPosition |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetLineOfPosition
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetLineOfPosition
ms.assetid: fe8d4802-ea16-49ca-8973-89dcaf6c915b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c916f0a76021afea82b4021ed1ce7d411317807
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087706"
---
# <a name="idebugdocumenttextgetlineofposition"></a>IDebugDocumentText::GetLineOfPosition
返回给定的字符位置的行号和对应的行中的字符偏移量 （可选）。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetLineOfPosition(  
   ULONG   cCharacterPosition,  
   ULONG*  pcLineNumber,  
   ULONG*  pcCharacterOffsetInLine  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cCharacterPosition`  
 [in]开始位置范围内的字符位置。  
  
 `pcLineNumber`  
 [out]范围的行数。  
  
 `pcCharacterOffsetInLine`  
 [in、 out]行中的范围的字符偏移量`pcLineNumber`。 如果此参数为`NULL`，该方法不返回值。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回的行号和对应的行中的字符偏移量 （可选） 到给定的字符位置。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentText 接口](../../winscript/reference/idebugdocumenttext-interface.md)