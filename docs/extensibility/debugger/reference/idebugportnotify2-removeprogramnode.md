---
title: IDebugPortNotify2::RemoveProgramNode |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortNotify2::RemoveProgramNode
helpviewer_keywords:
- IDebugPortNotify2::RemoveProgramNode
ms.assetid: 3668157b-66d2-416e-a359-fc04dcd18a48
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d837d349f17c78d3140f9516b1950a3415e30b89
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53879103"
---
# <a name="idebugportnotify2removeprogramnode"></a>IDebugPortNotify2::RemoveProgramNode
可以从其运行的端口进行调试的程序中注销。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT RemoveProgramNode(   
   IDebugProgramNode2* pProgramNode  
);  
```  
  
```csharp  
int RemoveProgramNode(   
   IDebugProgramNode2 pProgramNode  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pProgramNode`  
 [in][IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)对象，表示要注销的程序。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法中删除已添加到调用程序节点[AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)