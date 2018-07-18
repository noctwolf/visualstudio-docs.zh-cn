---
title: IDebugQueryEngine2::GetEngineInterface |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0e171805500322ff97feac0155abf50f32296366
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31117896"
---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
获取自定义调试引擎 (DE) 接口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetEngineInterface(   
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetEngineInterface(   
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppUnk`  
 [out]返回`IUnknown`对象，表示的调试引擎 (DE)，以及其中可以查询 DE 与关联的任何其他有效的接口 (例如[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)或[IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md))。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 应慎用生成接口，因为通过此方法从检索到的接口的调用绕过会话调试管理器的处理，并可能导致 SDM 使进入错误状态，或在调试时生成错误。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)