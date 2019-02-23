---
title: IEEVisualizerDataProvider::SetObjectForVisualizer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a55328c4148aa911d86b8f2daf05ba84a50ff444
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56711536"
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
此方法将更改该对象表示在可视化工具。

## <a name="syntax"></a>语法

```cpp
HRESULT SetObjectForVisualizer(
   IDebugObject*  pNewObject,
   BSTR*          error,
   IDebugObject** pException
);
```

```csharp
int SetObjectForVisualizer(
   IDebugObject     pNewObject,
   out string       error,
   out IDebugObject pException
);
```

#### <a name="parameters"></a>参数
 `pNewObject`

 [in]要设置的对象。

 `error`

 [out]如果将对象设置时出错，此字符串将包含错误消息。

 `pException`

 [out]如果出现错误，此对象将保存异常信息。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 它是由实现者确定如何返回错误信息。 但是，有可能某些调用方可能唯一的外观，以查看是否已返回的异常对象知道存在错误，因此如果出现错误，此方法始终应返回一个异常对象。 在调用方想要进行的情况下，也应提供的错误字符串使用它。

## <a name="see-also"></a>请参阅
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)