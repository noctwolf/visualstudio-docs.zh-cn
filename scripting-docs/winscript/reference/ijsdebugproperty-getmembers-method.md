---
title: 'Ijsdebugproperty:: Getmembers 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugProperty.GetMembers
apilocation:
- jscript9diag.dll
ms.assetid: a32b5372-d9cb-4b9a-9bc2-81b5e1df365c
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 351862f488aceb5fd3e9176cc4676e70b197d803
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087017"
---
# <a name="ijsdebugpropertygetmembers-method"></a>IJsDebugProperty::GetMembers 方法
获取此对象的成员。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetMembers(  
   JS_PROPERTY_MEMBERS members,  
   IJsEnumDebugProperty **ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `members`  
 [in]若要指定的成员信息中包含的内容的标志。  
  
 `ppEnum`  
 [out]对象的成员。  
  
## <a name="return-value"></a>返回值  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [IJsDebugProperty 接口](../../winscript/reference/ijsdebugproperty-interface.md)