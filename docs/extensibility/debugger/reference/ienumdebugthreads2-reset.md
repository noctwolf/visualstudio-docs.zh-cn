---
title: IEnumDebugThreads2::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugThreads2::Reset
helpviewer_keywords:
- IEnumDebugThreads2::Reset
ms.assetid: 88980d9a-c4d6-4de4-a9ab-fb56fa71394a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 83660f3689f34e9893c91c0a65dece64fa373cab
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54989869"
---
# <a name="ienumdebugthreads2reset"></a>IEnumDebugThreads2::Reset
将枚举重置为第一个元素。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法下, 一步调用后[下一步](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md)方法返回的第一个元素的枚举。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)