---
title: IDebugProgram2::GetProcess |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::GetProcess
helpviewer_keywords:
- IDebugProgram2::GetProcess
ms.assetid: 1d602485-ebaf-451c-9165-f2e226f20a90
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4a0e51725cf809e5c224fd438e507bcfde6ca2c5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31115939"
---
# <a name="idebugprogram2getprocess"></a>IDebugProgram2::GetProcess
获取此程序在运行时的进程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetProcess(  
   IDebugProcess2** ppProcess  
);  
```  
  
```csharp  
int GetProcess(  
   out IDebugProcess2 ppProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppProcess`  
 [out]返回[IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)表示进程的接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 除非调试引擎 (DE) 实现[IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)接口，此方法的 DE 的实现应始终返回`E_NOTIMPL`因为 DE 不能确定哪个进程正在运行，因此不能满足此方法的实现。  
  
 实现`IDebugEngineLaunch2`接口意味着 DE 必须了解如何创建进程; 因此，DE 的实施[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)接口是能够知道哪个进程在运行。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)