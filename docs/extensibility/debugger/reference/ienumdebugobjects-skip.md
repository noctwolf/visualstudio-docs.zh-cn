---
title: IEnumDebugObjects::Skip |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugObjects::Skip
helpviewer_keywords:
- IEnumDebugObjects::Skip method
ms.assetid: 957cead8-0a9c-4403-b190-b9fbadc49d42
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f212fbcd044f9d076b0505ac91a4f51b0ab89e29
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53883936"
---
# <a name="ienumdebugobjectsskip"></a>IEnumDebugObjects::Skip
此方法跳过指定数量的元素。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Skip(  
   [in] ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   [In] uint celt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]要跳过的元素数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果`celt`大于剩余的元素数; 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果`celt`指定的值数比大剩余元素的枚举设置为结束和`S_FALSE`返回。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)