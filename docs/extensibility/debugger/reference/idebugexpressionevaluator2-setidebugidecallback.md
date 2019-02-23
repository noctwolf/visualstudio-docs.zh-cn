---
title: IDebugExpressionEvaluator2::SetIDebugIDECallback | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2::SetIDebugIDECallback
- SetIDebugIDECallback
ms.assetid: f01c40ad-ef4b-477b-8304-602c6972bc88
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1ac5027421ff73e00ee34d9928be6525187a6ae8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56679289"
---
# <a name="idebugexpressionevaluator2setidebugidecallback"></a>IDebugExpressionEvaluator2::SetIDebugIDECallback
允许在初始化期间向表达式计算器传递回调调试引擎。

## <a name="syntax"></a>语法

```cpp
HRESULT SetIDebugIDECallback (
   IDebugIDECallback * pCallback
);
```

```csharp
int SetIDebugIDECallback (
   IDebugIDECallback pCallback
);
```

#### <a name="parameters"></a>参数
 `pCallback`

 [in]回调的接口。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)