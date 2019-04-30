---
title: IDebugExpressionEvaluationCompleteEvent2::GetResult | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluationCompleteEvent2::GetResult
helpviewer_keywords:
- IDebugExpressionEvaluationCompleteEvent2::GetResult
ms.assetid: d9ad3e22-b6b2-421e-9a43-6bb8c70d12a9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1cc3122103b075b18d2e77e72ad50cda958ba715
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62843178"
---
# <a name="idebugexpressionevaluationcompleteevent2getresult"></a>IDebugExpressionEvaluationCompleteEvent2::GetResult
获取表达式计算的结果。

## <a name="syntax"></a>语法

```cpp
HRESULT GetResult( 
   IDebugProperty2** ppResult
);
```

```csharp
int GetResult( 
   out IDebugProperty2 ppResult
);
```

#### <a name="parameters"></a>参数
 `ppResult`

 [out]返回[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)表示的表达式计算结果的对象。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 返回[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)对象包含的表达式的计算结果值。 请注意，此值可以是一个复杂的值，例如一个数组，但最终结果必须是数字或字符串向用户显示的值。

## <a name="see-also"></a>请参阅
- [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)