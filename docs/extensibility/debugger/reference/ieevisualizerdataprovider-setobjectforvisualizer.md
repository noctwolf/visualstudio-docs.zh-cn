---
title: IEEVisualizerDataProvider::SetObjectForVisualizer |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0d1a6272f8a04316c8695f301d5c45512b05f2d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
此方法可更改可视化工具表示的对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetObjectForVisualizer(  
   IDebugObject*  pNewObject,  
   BSTR*          error,  
   IDebugObject** pException  
);  
```  
  
```csharp  
int SetObjectForVisualizer(  
   IDebugObject     pNewObject,  
   out string       error,  
   out IDebugObject pException  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pNewObject`  
 [in]要设置的对象。  
  
 `error`  
 [out]如果没有设置该对象时出现错误，此字符串将包含错误消息。  
  
 `pException`  
 [out]如果没有错误，此对象包含的异常信息。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 它是取决于实施者，以确定如何返回错误信息。 但是，很可能某些调用方可能唯一查看，请参阅是否返回了异常对象以知道有错误，因此如果出错，此方法始终应返回异常对象。 在调用方想要对进行的情况下，还应提供的错误字符串使用它。  
  
## <a name="see-also"></a>另请参阅  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)