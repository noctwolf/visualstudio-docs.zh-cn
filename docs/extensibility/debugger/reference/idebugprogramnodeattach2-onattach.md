---
title: "IDebugProgramNodeAttach2::OnAttach |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords: IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a6b0f74ef5b14fb9e8971c0d539cc2e875658341
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
将附加到关联的程序或将推迟到 attach 进程[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT OnAttach(  
   [in] REFGUID guidProgramId  
);  
```  
  
```csharp  
int OnAttach(  
   ref Guid guidProgramId  
};  
```  
  
#### <a name="parameters"></a>参数  
 `guidProgramId`  
 [in]`GUID`要分配给关联的程序。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)不应该调用方法。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法之前调用附加过程中，[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)调用方法。 `OnAttach`方法可以执行附加过程本身 (在这种情况下，此方法返回`S_FALSE`) 或推迟到 attach 进程`IDebugEngine2::Attach`方法 (`OnAttach`方法返回`S_OK`)。 在既情况下，`OnAttach`方法可以设置`GUID`到正在调试的程序的给定`GUID`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)