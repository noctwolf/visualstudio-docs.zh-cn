---
title: "IDebugProgramProvider2::GetProviderProgramNode |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramProvider2::GetProviderProgramNode
helpviewer_keywords: IDebugProgramProvider2::GetProviderProgramNode
ms.assetid: e62e8e83-acbb-4c52-aedf-ffbd4670db29
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 150b2bc744329078319a3bf5d36dc0a97201c0c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramprovider2getproviderprogramnode"></a>IDebugProgramProvider2::GetProviderProgramNode
检索特定程序的程序节点。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetProviderProgramNode(  
   PROVIDER_FLAGS       Flags,  
   IDebugDefaultPort2*  pPort,  
   AD_PROCESS_ID        processId,  
   REFGUID              guidEngine,  
   UINT64               programId,  
   IDebugProgramNode2** ppProgramNode  
);  
```  
  
```csharp  
int GetProviderProgramNode(  
   enum_PROVIDER_FLAGS    Flags,  
   IDebugDefaultPort2     pPort,  
   AD_PROCESS_ID          ProcessId,  
   ref Guid               guidEngine,  
   ulong                  programId,  
   out IDebugProgramNode2 ppProgramNode  
);  
```  
  
#### <a name="parameters"></a>参数  
 `Flags`  
 [in]中的标志的组合[PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)枚举。 以下标志是典型的此调用：  
  
|Flag|描述|  
|----------|-----------------|  
|`PFLAG_REMOTE_PORT`|调用方远程计算机上运行。|  
|`PFLAG_DEBUGGEE`|当前正在调试调用方 （每个节点将返回有关封送处理的其他信息）。|  
|`PFLAG_ATTACHED_TO_DEBUGGEE`|调用方已附加到但不是由调试器启动。|  
  
 `pPort`  
 [in]调用进程的端口运行。  
  
 `processId`  
 [in][AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)保存包含的程序的进程 ID 问题的结构。  
  
 `guidEngine`  
 [in]（如果有），该程序附加到的调试引擎的 GUID。  
  
 `programId`  
 [in]要为其获取程序节点程序 ID。  
  
 `ppProgramNode`  
 [out][IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)对象，表示请求的程序节点。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)