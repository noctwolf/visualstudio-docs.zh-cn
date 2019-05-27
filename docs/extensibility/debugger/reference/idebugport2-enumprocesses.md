---
title: IDebugPort2::EnumProcesses | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPort2::EnumProcesses
helpviewer_keywords:
- IDebugPort2::EnumProcesses
ms.assetid: aafb32c5-5790-4807-a448-878a80256438
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 258a31a20a53dfdf9b9573a7a8fb9f53be1fc9ac
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66209328"
---
# <a name="idebugport2enumprocesses"></a>IDebugPort2::EnumProcesses
返回所有端口上运行的进程的列表。

## <a name="syntax"></a>语法

```cpp
HRESULT EnumProcesses( 
   IEnumDebugProcesses2** ppEnum
);
```

```csharp
int EnumProcesses( 
   out IEnumDebugProcesses2 ppEnum
);
```

## <a name="parameters"></a>参数
`ppEnum`\
[out]返回[IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)对象，其中包含的所有端口上运行的进程列表。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)