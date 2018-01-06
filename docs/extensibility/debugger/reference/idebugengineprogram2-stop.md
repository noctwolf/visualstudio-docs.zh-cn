---
title: "IDebugEngineProgram2::Stop |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngineProgram2::Stop
helpviewer_keywords: IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4004ca92b32e63565a71a3a6971ebb4ae073b9f9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
  
## <a name="see-also"></a>请参阅  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)