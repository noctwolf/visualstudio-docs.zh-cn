---
title: IDebugProgramProvider2::GetProviderProgramNode | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramProvider2::GetProviderProgramNode
helpviewer_keywords:
- IDebugProgramProvider2::GetProviderProgramNode
ms.assetid: e62e8e83-acbb-4c52-aedf-ffbd4670db29
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c468745418c01b638cbc407342820b9127b460b6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62869810"
---
# <a name="idebugprogramprovider2getproviderprogramnode"></a>IDebugProgramProvider2::GetProviderProgramNode
检索特定程序的程序节点。

## <a name="syntax"></a>语法

```cpp
HRESULT GetProviderProgramNode(
   PROVIDER_FLAGS       Flags,
   IDebugDefaultPort2*  pPort,
   AD_PROCESS_ID        processId,
   REFGUID              guidEngine,
   UINT64               programId,
   IDebugProgramNode2** ppProgramNode
);
```

```csharp
int GetProviderProgramNode(
   enum_PROVIDER_FLAGS    Flags,
   IDebugDefaultPort2     pPort,
   AD_PROCESS_ID          ProcessId,
   ref Guid               guidEngine,
   ulong                  programId,
   out IDebugProgramNode2 ppProgramNode
);
```

#### <a name="parameters"></a>参数
 `Flags`

 [in]中的标志的组合[PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)枚举。 下列标志则典型的此调用：

|Flag|描述|
|----------|-----------------|
|`PFLAG_REMOTE_PORT`|调用方在远程计算机上运行。|
|`PFLAG_DEBUGGEE`|当前正在调试调用方 （为每个节点将返回有关封送处理的其他信息）。|
|`PFLAG_ATTACHED_TO_DEBUGGEE`|调用方已附加到但不是启动调试器。|

 `pPort`

 [in]调用进程的端口上运行。

 `processId`

 [in][AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)保存包含该程序的进程的 ID 相关的结构。

 `guidEngine`

 [in]（如果有），该程序附加到的调试引擎的 GUID。

 `programId`

 [in]若要获取的程序节点的程序的 ID。

 `ppProgramNode`

 [out][IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)对象，表示请求的程序节点。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)
- [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)
- [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)