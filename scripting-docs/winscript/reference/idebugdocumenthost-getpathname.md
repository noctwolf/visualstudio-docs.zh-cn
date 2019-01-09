---
title: IDebugDocumentHost::GetPathName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.GetPathName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::GetPathName
ms.assetid: 8abe2a86-e467-4ac9-8ccb-8761141bfa0d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c33844ade2367ffeb7690306a5febbabde2f016
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096026"
---
# <a name="idebugdocumenthostgetpathname"></a>IDebugDocumentHost::GetPathName
返回文档的源文件的完整路径和文件名称。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrLongName`  
 [out]包含长名称的字符串。  
  
 `pfIsOriginalFile`  
 [out]一个标志，它是如果`pbstrLongName`否则引用的原始文件为 false 的文档。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_FAIL`|可以创建或确定任何源文件。|  
  
## <a name="remarks"></a>备注  
 此方法返回文档的源文件的完整路径和文件的名称。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentHost 接口](../../winscript/reference/idebugdocumenthost-interface.md)