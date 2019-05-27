---
title: IDebugPortEx2::GetPortProcessId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2::GetPortProcessId
helpviewer_keywords:
- IDebugPortEx2::GetPortProcessId
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: bdc0dc1155c3ceffa5e784279f113a8c7d30a168
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66209073"
---
# <a name="idebugportex2getportprocessid"></a>IDebugPortEx2::GetPortProcessId
获取自身的端口的进程 ID。

## <a name="syntax"></a>语法

```cpp
HRESULT GetPortProcessId ( 
   DWORD* pdwProcessId
);
```

```csharp
int GetPortProcessId ( 
   out uint pdwProcessId
);
```

## <a name="parameters"></a>参数
`pdwProcessId`\
[out]返回自身的端口的物理进程 ID。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 Win32 运行时中，此方法通常会调用 Win32 函数`GetCurrentProcessId`以获取物理进程 id。

## <a name="see-also"></a>请参阅
- [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)