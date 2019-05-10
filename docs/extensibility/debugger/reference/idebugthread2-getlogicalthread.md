---
title: IDebugThread2::GetLogicalThread | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::GetLogicalThread
helpviewer_keywords:
- IDebugThread2::GetLogicalThread
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9e57d3deac01b00f1f332b34075d74f6402235f4
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65224027"
---
# <a name="idebugthread2getlogicalthread"></a>IDebugThread2::GetLogicalThread
调试引擎不会实现此方法。

## <a name="syntax"></a>语法

```cpp
HRESULT GetLogicalThread( 
   IDebugStackFrame2*     pStackFrame,
   IDebugLogicalThread2** ppLogicalThread
);
```

```csharp
int GetLogicalThread( 
   IDebugStackFrame2        pStackFrame,
   out IDebugLogicalThread2 ppLogicalThread
);
```

## <a name="parameters"></a>参数
 `pStackFrame`\

 [in][IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)对象，表示堆栈帧。

 `ppLogicalThread`\

 [out]返回`IDebugLogicalThread2`接口，表示关联的逻辑线程。 调试引擎实现应设置为 null 值。

## <a name="return-value"></a>返回值
 调试引擎实现始终返回`E_NOTIMPL`。

## <a name="see-also"></a>请参阅
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)