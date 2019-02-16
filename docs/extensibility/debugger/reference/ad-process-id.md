---
title: AD_PROCESS_ID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- AD_PROCESS_ID
helpviewer_keywords:
- AD_PROCESS_ID union
ms.assetid: 4cb40d12-2e92-4f09-83f4-689928bd65b3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e03b51081b082c1180091e823eead47a21a7b3d2
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315425"
---
# <a name="adprocessid"></a>AD_PROCESS_ID
指定的进程 ID，这可能是系统 ID 或 GUID。

## <a name="syntax"></a>语法

```cpp
typedef struct _AD_PROCESS_ID {
    AD_PROCESS_ID_TYPE ProcessIdType;
    union {
        DWORD dwProcessId; 
        GUID  guidProcessId; 
        DWORD dwUnused; 
    } ProcessId;
} AD_PROCESS_ID;
```

```csharp
public struct AD_PROCESS_ID {
    AD_PROCESS_ID_TYPE ProcessIdType;
    DWORD              dwProcessId; 
    GUID               guidProcessId; 
    DWORD              dwUnused; 
};
```

## <a name="members"></a>成员
`ProcessIdType`  
中的值[AD_PROCESS_ID_TYPE](../../../extensibility/debugger/reference/ad-process-id-type.md)枚举，它指定如何解释`ProcessId`union （或者，对于托管代码，该结构的成员才能访问）。

dwProcessId  
从系统值形式的进程 ID。

guidProcessId  
以 GUID 形式表示的进程 ID。

dwUnused  
填充量。

## <a name="remarks"></a>备注
此结构传递给以下方法：

- [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)

- [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)

- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)

- [GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)

及返回的以下方法：

- [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)

- [GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
[结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)  
[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)  
[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)  
[AD_PROCESS_ID_TYPE](../../../extensibility/debugger/reference/ad-process-id-type.md)  
[GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
[GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)  
[GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)  
[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)  
[GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)
