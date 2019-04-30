---
title: IDebugEngine2::CauseBreak |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::CauseBreak
helpviewer_keywords:
- IDebugEngine2::CauseBreak
ms.assetid: 17fe4698-b04e-4798-8412-80e0da60c387
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fa0d559887019a697b820a5a6c91f80b78c6b713
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920954"
---
# <a name="idebugengine2causebreak"></a>IDebugEngine2::CauseBreak
一个其线程尝试运行所有程序 (DE) 停止执行下一次此调试引擎正在调试的请求。

## <a name="syntax"></a>语法

```cpp
HRESULT CauseBreak( 
   void 
);
```

```csharp
int CauseBreak();
```

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 此方法是异步的： [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)接下来，该程序尝试执行后调用此方法则会发送事件。

## <a name="see-also"></a>请参阅
- [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)