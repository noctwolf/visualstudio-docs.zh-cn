---
title: IDebugPort2::GetProcess |Microsoft Docs
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
- IDebugPort2::GetPortSupplier
helpviewer_keywords:
- IDebugPort2::GetPortSupplier
ms.assetid: 3e2431b0-0e19-450d-8e1d-d7c314c8f872
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 04acaa62840eaf96bcb1408ac9f28a3a15ab819d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49825424"
---
# <a name="idebugport2getprocess"></a>IDebugPort2::GetProcess
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取指定的端口上运行的进程。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetProcess(   
   AD_PROCESS_ID    ProcessId,  
   IDebugProcess2** ppProcess  
);  
```  
  
```csharp  
int GetProcess(   
   AD_PROCESS_ID      ProcessId,  
   out IDebugProcess2 ppProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ProcessId`  
 [in][AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)结构，它指定的进程标识符。  
  
 `ppProcess`  
 [out]返回[IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)表示进程的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)

