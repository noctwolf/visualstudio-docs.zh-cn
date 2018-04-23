---
title: IDebugCodeContext3 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 451e61ab7d6f74c83898987cdbecad2a9e13b06c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
扩展[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)接口要启用的模块和过程接口检索。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 由的调试引擎实现，且由使用[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]调试包。  
  
## <a name="methods"></a>方法  
 除了上的方法`IDebugCodeContext2`接口，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|检索到的调试模块接口的引用。|  
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|检索到调试进程的接口的引用。|  
  
## <a name="remarks"></a>备注  
 这是通常不需要实现的可选接口。  
  
## <a name="requirements"></a>要求  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll