---
title: IDebugExceptionEvent2::CanPassToDebuggee |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
ms.assetid: ae4bbe0a-fbe1-49be-a310-ea64279a434b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 93652efe19096466c853d758cc36aa022236068d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920097"
---
# <a name="idebugexceptionevent2canpasstodebuggee"></a>IDebugExceptionEvent2::CanPassToDebuggee
确定调试引擎 (DE) 支持将此异常传递给执行恢复时正在调试的程序的选项。

## <a name="syntax"></a>语法

```cpp
HRESULT CanPassToDebuggee(
   void
);
```

```csharp
int CanPassToDebuggee();
```

## <a name="return-value"></a>返回值
 返回`S_OK`（异常可以传递到该程序） 或`S_FALSE`（不能将异常传递）。

## <a name="remarks"></a>备注
 DE 必须传递到调试对象的默认操作。 IDE 可能会收到[IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)事件，并调用[继续](../../../extensibility/debugger/reference/idebugprocess3-continue.md)方法而无需调用`CanPassToDebuggee`方法。 因此，DE 应具有默认分支或不传递异常。

## <a name="see-also"></a>请参阅
- [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)
- [Continue](../../../extensibility/debugger/reference/idebugprocess3-continue.md)