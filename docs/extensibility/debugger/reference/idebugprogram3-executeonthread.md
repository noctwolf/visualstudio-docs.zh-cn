---
title: IDebugProgram3::ExecuteOnThread |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugProgram3::ExecuteOnThread
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: afca4a97380d010897ca1dfb7c6229f3f1897ef9
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49865935"
---
# <a name="idebugprogram3executeonthread"></a>IDebugProgram3::ExecuteOnThread
执行调试程序。 线程将返回以授予用户查看哪个线程执行程序时的调试程序信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ExecuteOnThread(  
   [in] IDebugThread2* pThread)  
```  
  
```csharp  
int ExecuteOnThread(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pThread`  
 [in][IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 有三种不同方法，调试器可以恢复后停止执行：  
  
- 执行： 取消任何上一步骤中，并运行到下一个断点，依此类推。  
  
- 步骤： 取消任何旧的步骤，并运行，直到新的步骤完成。  
  
- 继续： 再次运行，并保留任何旧步骤活动。  
  
  在线程传递给`ExecuteOnThread`决定哪个步骤取消时很有用。 如果不知道运行的线程，执行将取消所有步骤。 线程的信息后，只需取消对活动线程的步骤。  
  
## <a name="see-also"></a>请参阅  
 [执行](../../../extensibility/debugger/reference/idebugprogram2-execute.md)   
 [IDebugProgram3](../../../extensibility/debugger/reference/idebugprogram3.md)