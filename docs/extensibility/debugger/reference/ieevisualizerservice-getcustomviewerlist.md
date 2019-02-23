---
title: IEEVisualizerService::GetCustomViewerList |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerService::GetCustomViewerList
helpviewer_keywords:
- IEEVisualizerService::GetCustomViewerList method
ms.assetid: 249d26ca-914f-43af-a400-8162477223f4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 00a7928b203d00e0f9b43250a463a8fb272ce755
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694109"
---
# <a name="ieevisualizerservicegetcustomviewerlist"></a>IEEVisualizerService::GetCustomViewerList
此方法返回此服务知道的类型可视化工具的列表。

## <a name="syntax"></a>语法

```cpp
HRESULT GetCustomViewerList(
   ULONG                celtSkip,
   ULONG                celtRequested,
   DEBUG_CUSTOM_VIEWER* rgViewers,
   ULONG*               pceltFetched
);
```

```csharp
int GetCustomViewerList(
   uint                  celtSkip,
   uint                  celtRequested,
   DEBUG_CUSTOM_VIEWER[] rgViewers,
   out uint              pceltFetched
);
```

#### <a name="parameters"></a>参数
 `celtSkip`

 [in]可视化工具，以便跳过的数。

 `celRequested`

 [in]可视化工具，以便检索数 (还指定了大小的`rgViewers`数组)。

 `rgViewers`

 [in、 out]数组[DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)要填充的结构。

 `pceltFetched`

 [out]实际检索的可视化工具数。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
- [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)将请求传递给此方法作为其支持的一部分的类型可视化工具。 如果表达式计算器还提供了相同类型的自定义查看器，它可以追加相应地填充扩展[DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)列表对这些自定义查看器的结构。 请确保[GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)反映了这些附加的浏览器。

 请参阅[类型可视化工具和自定义查看器](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)有关可视化工具和查看器之间的差异的详细信息。

## <a name="see-also"></a>请参阅
- [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)
- [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)
- [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)
- [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)
- [类型可视化工具和自定义查看器](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)