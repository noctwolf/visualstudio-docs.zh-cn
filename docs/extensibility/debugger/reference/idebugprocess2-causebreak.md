---
title: "IDebugProcess2::CauseBreak |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::CauseBreak
helpviewer_keywords: IDebugProcess2::CauseBreak
ms.assetid: efda8865-2319-4d53-90bf-6d9d74cd5195
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 99047f7703f39a04049162686079ed26ad9b30f8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess2causebreak"></a>IDebugProcess2::CauseBreak
下一步，它是程序在此过程中的运行代码的请求暂停，并发送[IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)事件对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CauseBreak(   
   void  
);  
```  
  
```csharp  
int CauseBreak();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)