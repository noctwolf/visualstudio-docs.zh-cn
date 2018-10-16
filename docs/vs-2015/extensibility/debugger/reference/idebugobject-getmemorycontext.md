---
title: IDebugObject::GetMemoryContext |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugObject::GetMemoryContext
helpviewer_keywords:
- IDebugObject::GetMemoryContext method
ms.assetid: 6760a0d3-a898-4e81-b68f-c45c584b225b
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a6a37b24df1310218c5e4d68df5109ec59eb7b1d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49203614"
---
# <a name="idebugobjectgetmemorycontext"></a>IDebugObject::GetMemoryContext
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取表示对象的值的地址的内存上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetMemoryContext(   
   IDebugMemoryContext2** pContext  
);  
```  
  
```csharp  
int GetMemoryContext(  
   ref IDebugMemoryContext2 pContext  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pContext`  
 [out]返回[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)对象，表示对象的值的地址。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 返回的内存上下文指定值的地址，如由此[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象。  
  
## <a name="see-also"></a>请参阅  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)

