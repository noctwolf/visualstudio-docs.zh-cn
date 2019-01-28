---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8393eb7bc712de28e2378a9ad09081efe76eca6b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54933940"
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7

> [!Note]
> 不推荐使用。 不要使用。

## <a name="syntax"></a>语法

```cpp
HRESULT DetachDebugger_V7 (
   void 
);
```

```csharp
int DetachDebugger_V7 ();
```

## <a name="return-value"></a>返回值

实现应始终返回`E_NOTIMPL`。

## <a name="remarks"></a>备注

> [!WARNING]
> Visual Studio 2005 中，在撰写此方法不再使用，应始终返回`E_NOTIMPL`。

调试器会意外退出时，调用此方法。 调用此方法时，DE 应恢复该程序，就好像用户从其分离。 应发送没有更多的调试事件。 程序应该可附加成员在调试器的另一个实例的状态。

## <a name="see-also"></a>请参阅

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)