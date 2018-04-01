---
title: IDebugProgramEx2::Attach |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgramEx2::Attach
helpviewer_keywords:
- IDebugProgramEx2::Attach
ms.assetid: 33b22b2f-431e-4205-9441-d28a9c928c97
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 440a4ce6b008efe541187d1d99d886f4c7c5f9ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramex2attach"></a>IDebugProgramEx2::Attach
附加到某个程序的会话。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason,  
   IDebugSession2*       pSession  
);  
```  
  
```  
[C#]  
int Attach(   
   IDebugEventCallback2 pCallback,  
   uint                 dwReason,  
   IDebugSession2       pSession  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pCallback`  
 [in][IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)对象，表示附加的调试引擎将发送到事件的回调函数。  
  
 `dwReason`  
 [in]取值范围为[ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)说明原因的附加操作的枚举。  
  
 `pSession`  
 [in]一个值，唯一标识会话的附加到的程序。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。 此方法应返回`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`如果程序已连接。  
  
## <a name="remarks"></a>备注  
 包含的程序的端口可以使用中的值`pSession`来确定哪些会话尝试附加到程序。 例如，如果端口允许只有一个调试会话才能一次附加到进程，可以确定端口是否同一个会话已附加到进程中的其他程序。  
  
> [!NOTE]
>  接口中进行传递`pSession`是仅视为 cookie，用于唯一标识会话调试管理器附加到此程序; 的值上提供的接口的方法都正常工作。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)