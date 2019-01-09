---
title: IDebugProperty::GetPropertyInfo |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.GetPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetPropertyInfo
ms.assetid: b201c0c4-bff6-4285-880f-67be90584c5f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7db7403f4f7fc737145db8b4a395a865a82ef56
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095623"
---
# <a name="idebugpropertygetpropertyinfo"></a>IDebugProperty::GetPropertyInfo
获取的值`IDebugProperty`描述一种方法或索引的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetPropertyInfo (  
   DBGPROP_INFO_FLAGSdwFields,  
   UINT nRadix,  
   DebugPropertyInfo* pPropertyInfo  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwFields`  
 [in]指定`DBGPROP_INFO_FLAGS`确定要在中填写的字段的常量`DebugPropertyInfo`结构。  
  
 `nRadix`  
 [in]用于格式化数值的任何信息的基数。  
  
 `pPropertyInfo`  
 [out]返回`DebugPropertyInfo`描述的属性的结构。  
  
## <a name="return-value"></a>返回值  
 返回一个有效`HRESULT`，通常`S_OK`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty 接口](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)   
 [DebugPropertyInfo 结构](../../winscript/reference/debugpropertyinfo-structure.md)