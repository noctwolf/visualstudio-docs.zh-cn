---
title: IDebugProperty2::GetMemoryContext |Microsoft Docs
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
- IDebugProperty2::GetMemoryContext
helpviewer_keywords:
- IDebugProperty2::GetMemoryContext
ms.assetid: 91793d25-790f-4881-a5c0-d0458e534514
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 13c65c1a6abd0123ab161ca035f3f5d4372db22d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49201781"
---
# <a name="idebugproperty2getmemorycontext"></a>IDebugProperty2::GetMemoryContext
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取属性值的内存上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetMemoryContext (   
   IDebugMemoryContext2** ppMemory  
);  
```  
  
```csharp  
int GetMemoryContext(  
   out IDebugMemoryContext2 ppMemory  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppMemory`  
 [out]返回[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)对象，表示与此属性关联的内存。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。 返回`S_GETMEMORYCONTEXT_NO_MEMORY_CONTEXT`如果没有内存上下文来检索。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)

