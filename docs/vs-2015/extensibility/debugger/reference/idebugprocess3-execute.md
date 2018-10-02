---
title: IDebugProcess3::Execute |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProcess3::Execute
helpviewer_keywords:
- IDebugProcess3::Execute
ms.assetid: d831cd81-d7bf-4172-8517-aa699867791f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8e727d58c9287077364b851f5ade18f89eebd248
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468960"
---
# <a name="idebugprocess3execute"></a>IDebugProcess3::Execute
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProcess3::Execute](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess3-execute)。  
  
将继续运行此过程从已停止状态。 清除任何以前的执行状态 （如步骤），并再次执行该过程开始。  
  
> [!NOTE]
>  应使用此方法以代替[Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md)。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Execute(  
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Execute(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pThread`  
 [in][IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)对象，表示要执行的线程。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为将返回错误代码。  
  
## <a name="remarks"></a>备注  
 当用户从某个其他进程的线程已停止状态开始执行时，对此过程将调用此方法。 当用户选择此方法也称为**启动**命令**调试**菜单在 IDE 中的。 此方法的实现可能很简单，与调用[Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)过程中在当前线程上的方法。  
  
> [!WARNING]
>  不发送停止事件或将即时 （同步） 事件与[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)时处理此调用; 否则调试器可能会挂起。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [恢复](../../../extensibility/debugger/reference/idebugthread2-resume.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)

