---
title: "IDebugPortEx2::CanTerminateProcess |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortEx2::CanTerminateProcess
helpviewer_keywords: IDebugPortEx2::CanTerminateProcess
ms.assetid: 111f65d8-5a1a-42b3-9de3-dd9bb03a33fd
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 023611e20f8df50a3d07086d6600b1622f1b69be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportex2canterminateprocess"></a>IDebugPortEx2::CanTerminateProcess
确定是否可以终止进程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CanTerminateProcess(   
   IDebugProcess2* pPortProcess  
);  
```  
  
```csharp  
HRESULT CanTerminateProcess(   
   IDebugProcess2 pPortProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pPortProcess`  
 [in][IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)对象表示要终止进程。  
  
## <a name="return-value"></a>返回值  
 返回`S_OK`如果进程可以终止; 否则，返回`S_FALSE`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)