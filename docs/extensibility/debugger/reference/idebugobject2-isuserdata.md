---
title: "IDebugObject2::IsUserData |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject2::IsUserData
helpviewer_keywords: IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5cd56e2b83411710fa110c7abd65d965d828083d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
确定对象是否表示用户数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsUserData(  
   BOOL* pfUser  
);  
```  
  
```csharp  
int IsUserData(  
   out int pfUser  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pfUser`  
 [out]返回非零 (`TRUE`) 表示的对象的用户数据; 如果零 (`FALSE`) 如果它不存在。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 用户数据是指定为 JustMyCode （将模块标记为用户代码和堆栈跟踪中因此可见的用户可配置选项） 模块的一部分的任何对象。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)