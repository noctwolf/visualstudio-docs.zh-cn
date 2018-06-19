---
title: IDebugEngineProgram2::Stop |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::Stop
helpviewer_keywords:
- IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ab5bec65dc3f53681d40743bea694295ff69944b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31113850"
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
停止所有线程在此程序中运行。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Stop(   
   void   
);  
```  
  
```csharp  
int Stop();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此程序在调试多程序环境中时，调用此方法。 当收到某个其他程序中的停止事件时，在此程序上调用此方法。 此方法的实现应是异步的;即，并非所有的线程应需要此方法返回之前停止。 此方法的实现可能很简单，只需与调用[CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)于此程序的方法。  
  
 此方法的响应情况下，会不发送任何调试事件。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)