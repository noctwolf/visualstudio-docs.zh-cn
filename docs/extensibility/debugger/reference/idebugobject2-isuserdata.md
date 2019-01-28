---
title: IDebugObject2::IsUserData | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugObject2::IsUserData
helpviewer_keywords:
- IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 33b6815f5d216e4259c7e43dad11ca93ab1a3776
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55015623"
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
确定对象是否表示用户数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsUserData(  
   BOOL* pfUser  
);  
```  
  
```csharp  
int IsUserData(  
   out int pfUser  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pfUser`  
 [out]返回非零值 (`TRUE`) 如果该对象表示用户数据; 零 (`FALSE`) 如果不是。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 用户数据是任何对象，并且指定为 JustMyCode （将模块标记为用户代码和堆栈跟踪中因此可见用户可配置选项） 模块的一部分。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)