---
title: "IDebugProgramEngines2::SetEngine |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEngines2::SetEngine
helpviewer_keywords: IDebugProgramEngines2::SetEngine
ms.assetid: c05857ee-89cf-455e-8f1e-300cce4a2eab
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ee86986b531b2dcadefc9b3be6d5e5d1ff87f46d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramengines2setengine"></a>IDebugProgramEngines2::SetEngine
通知的程序或程序节点的调试引擎 (DE) 要用于调试此程序。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetEngine(   
   REFGUID guidEngine  
);  
```  
  
```csharp  
int SetEngine(   
   ref Guid guidEngine  
);  
```  
  
#### <a name="parameters"></a>参数  
 `guidEngine`  
 [in]DE 的 GUID。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)