---
title: IDebugExpressionEvaluator2::GetService | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2::GetService
- GetService
ms.assetid: f8988a9e-9d18-42af-84a7-55f41e9adf63
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ac6f73e31e7e15a2ffd86e2d969f98a686fbd004
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842927"
---
# <a name="idebugexpressionevaluator2getservice"></a>IDebugExpressionEvaluator2::GetService
检索服务对象给出它的唯一标识符。

## <a name="syntax"></a>语法

```cpp
HRESULT GetService (
   GUID        uid,
   IUnknown ** ppService
);
```

```csharp
int GetService (
   Guid       uid,
   out object ppService
);
```

#### <a name="parameters"></a>参数
 `uid`

 [in]要检索的服务的唯一标识符。

 `ppService`

 [out]返回一个对象，表示该服务。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 这可供第三方表达式计算器才能获取另一个表达式计算器中的服务。 例如，此方法无法用于从默认表达式计算器获取可视化工具服务接口。 第三方表达式计算器不太可能需要实现此接口。

## <a name="see-also"></a>请参阅
- [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)