---
title: IDebugProgramEngines2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramEngines2
helpviewer_keywords:
- IDebugProgramEngines2 interface
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a383dc55b42fe8baad8df31628d0a182d50d554e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55025665"
---
# <a name="idebugprogramengines2"></a>IDebugProgramEngines2
此接口由程序节点用于指定所有可能的调试引擎 (DE)，可以调试该程序。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProgramEngines2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 DE 或自定义端口提供程序实现此接口上实现的相同对象[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)以支持建立特定部署要用于特定的程序。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[QueryInterface](/cpp/atl/queryinterface)上`IDebugProgramNode2`接口，以获得此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugProgramEngines2`。  
  
|方法|描述|  
|------------|-----------------|  
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|指示可以调试该程序的所有可能的 DEs。|  
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|选择要用于调试此程序 DE。|  
  
## <a name="remarks"></a>备注  
 一旦用户选择部署后，选择是否已注册程序节点通过调用[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)。 所选的引擎将成为由返回的引擎[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)