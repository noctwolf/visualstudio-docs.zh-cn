---
title: IDebugEngineLaunch2::LaunchSuspended |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineLaunch2::LaunchSuspended
helpviewer_keywords:
- IDebugEngineLaunch2::LaunchSuspended
ms.assetid: 5dd2643e-c20a-470e-9024-2a423eb39856
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a05e8f034ec30f0f387675759cb7601f7b3fc3e7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31114620"
---
# <a name="idebugenginelaunch2launchsuspended"></a>IDebugEngineLaunch2::LaunchSuspended
此方法通过调试引擎 (DE) 启动进程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LaunchSuspended (   
   LPCOLESTR             pszMachine,  
   IDebugPort2*          pPort,  
   LPCOLESTR             pszExe,  
   LPCOLESTR             pszArgs,  
   LPCOLESTR             pszDir,  
   BSTR                  bstrEnv,  
   LPCOLESTR             pszOptions,  
   LAUNCH_FLAGS          dwLaunchFlags,  
   DWORD                 hStdInput,  
   DWORD                 hStdOutput,  
   DWORD                 hStdError,  
   IDebugEventCallback2* pCallback,  
   IDebugProcess2**      ppDebugProcess  
);  
```  
  
```csharp  
int LaunchSuspended(  
   string               pszServer,   
   IDebugPort2          pPort,   
   string               pszExe,   
   string               pszArgs,   
   string               pszDir,   
   string               bstrEnv,   
   string               pszOptions,   
   enum_LAUNCH_FLAGS    dwLaunchFlags,   
   uint                 hStdInput,   
   uint                 hStdOutput,   
   uint                 hStdError,  
   IDebugEventCallback2 pCallback,   
   out IDebugProcess2   ppProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszMachine`  
 [in]中用于启动进程的计算机的名称。 使用 null 值来指定本地计算机。  
  
 `pPort`  
 [in][IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)接口，表示该程序将运行中的端口。  
  
 `pszExe`  
 [in]若要启动的可执行文件的名称。  
  
 `pszArgs`  
 [in]要传递到可执行文件的参数。 如果没有任何参数，则可能是 null 值。  
  
 `pszDir`  
 [in]由可执行文件的工作目录的名称。 如果没有工作目录是必需的则可能是 null 值。  
  
 `bstrEnv`  
 [in]以 NULL 结尾的字符串，跟附加 NULL 终止符的环境块。  
  
 `pszOptions`  
 [in]有关可执行文件的选项。  
  
 `dwLaunchFlags`  
 [in]指定[LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)会话。  
  
 `hStdInput`  
 [in]备用的输入流的句柄。 如果不需要重定向，则可能为 0。  
  
 `hStdOutput`  
 [in]备用输出流的句柄。 如果不需要重定向，则可能为 0。  
  
 `hStdError`  
 [in]备用错误输出流的句柄。 如果不需要重定向，则可能为 0。  
  
 `pCallback`  
 [in][IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)接收调试器事件的对象。  
  
 `ppDebugProcess`  
 [out]返回生成[IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)表示启动的进程的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 通常情况下，[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]启动程序使用[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)方法，然后将调试器附加到挂起的程序。 但是，有一些情况下在其中的调试引擎可能需要在这种情况下启动 （例如，如果调试引擎是解释器的一部分，正在调试的程序是一个解释的语言），某个程序[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]使用`IDebugEngineLaunch2::LaunchSuspended`方法.  
  
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)调用方法以在过程已成功启动处于挂起状态后启动该进程。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)