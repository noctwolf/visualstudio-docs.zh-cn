---
title: IObjectIdentity::IsEqualObject |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IObjectIdentity.IsEqualObject
apilocation:
- scrobj.dll
helpviewer_keywords:
- IsEqualObject method
ms.assetid: 78c5c5c2-d299-4036-986c-7c1d87cbe7cd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa233e478c83b723b13d19d27dc4b63ee4700bb5
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095051"
---
# <a name="iobjectidentityisequalobject"></a>IObjectIdentity::IsEqualObject
确定对象是否等于当前对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT IsEqualObject(  
  IUnknown*punk  
);  
```  
  
#### <a name="parameters"></a>参数  
 `punk`  
 [in]要与当前对象进行比较的对象的地址。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|对象相等。|  
|`S_FALSE`|对象不相等。|  
  
## <a name="remarks"></a>备注  
 实现`IsEqualObject`方法应返回`S_OK`仅当对象是否相同。  
  
## <a name="see-also"></a>请参阅  
 [IObjectIdentity 接口](../../winscript/reference/iobjectidentity-interface.md)