---
title: IEnumDebugPropertyInfo::Skip |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugPropertyInfo.Skip
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugPropertyInfo::Skip
ms.assetid: 2f6361fb-d66d-4fc0-8fe0-c859593a183f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72445473a1fe090a468010b33381e8751f1bbc65
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096507"
---
# <a name="ienumdebugpropertyinfoskip"></a>IEnumDebugPropertyInfo::Skip
跳过指定的数目的`DebugPropertyInfo`枚举序列中的结构。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Skip(  
   ULONGcelt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]数`DebugPropertyInfo`要跳过枚举序列中的结构。  
  
## <a name="return-value"></a>返回值  
 返回一个有效`HRESULT`，通常`S_OK`。 返回`S_FALSE`，并将当前元素指针设置到枚举末尾，如果`celt`大于枚举器中剩余的元素数。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugPropertyInfo 接口](../../winscript/reference/ienumdebugpropertyinfo-interface.md)   
 [DebugPropertyInfo 结构](../../winscript/reference/debugpropertyinfo-structure.md)