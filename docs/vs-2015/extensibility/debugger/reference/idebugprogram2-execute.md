---
title: IDebugProgram2::Execute |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgram2::Execute
helpviewer_keywords:
- IDebugProgram2::Execute
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 59817468007a595c396f174f5205e124fe65d015
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49900756"
---
# <a name="idebugprogram2execute"></a>IDebugProgram2::Execute
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

将继续运行此程序从已停止状态。 清除任何以前的执行状态 （如步骤），然后再次执行该程序开始。  
  
> [!NOTE]
>  此方法已弃用。 使用[Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Execute(  
   void  
);  
```  
  
```csharp  
int Execute();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 当用户从其他程序中的线程已停止状态开始执行时，此程序上调用此方法。 当用户选择此方法也称为**启动**命令**调试**菜单在 IDE 中的。 此方法的实现可能很简单，与调用[Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)程序中的当前线程上的方法。  
  
> [!WARNING]
>  不发送停止事件或将即时 （同步） 事件与[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)时处理此调用; 否则调试器可能会挂起。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)

