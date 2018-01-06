---
title: "IDebugProgramEngines2 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEngines2
helpviewer_keywords: IDebugProgramEngines2 interface
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8e4830c43fbffeb4f7df627f859e6fd48a4387a7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramengines2"></a>IDebugProgramEngines2
程序节点使用此接口来指定所有可能的调试引擎 (DE)，可以调试此程序。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProgramEngines2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 DE 或自定义端口供应商实现此接口上实现的相同对象[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)以支持建立特定 DE 要为特定的程序使用。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[QueryInterface](/cpp/atl/queryinterface)上`IDebugProgramNode2`接口，以获得此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugProgramEngines2`。  
  
|方法|描述|  
|------------|-----------------|  
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|指示可以调试此程序的所有可能 DEs。|  
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|选择要用于调试此程序 DE。|  
  
## <a name="remarks"></a>备注  
 使用程序的节点注册该选择由用户选择 DE 后，通过调用[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)。 所选的引擎将成为由返回的引擎[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)