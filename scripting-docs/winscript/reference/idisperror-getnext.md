---
title: IDispError::GetNext |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetNext
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetNext
ms.assetid: 3e5267f8-ba62-41c3-bd3e-eced2ad85e8e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 98a9d728429c302f6ac7d865d8ace9b92dbf4c2e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097495"
---
# <a name="idisperrorgetnext"></a>IDispError::GetNext
检索下一个`IDispError`对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetNext(  
   IDispError**  ppde  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppde`  
 [out]接下来指定`IDispError`对象。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法检索下一个`IDispError`对象。 如果这是最后`IDispError`对象，此方法将返回 NULL。  
  
> [!NOTE]
>  未实现此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDispError 接口](../../winscript/reference/idisperror-interface.md)