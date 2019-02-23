---
title: IDebugProcessEx2::Attach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcessEx2::Attach
helpviewer_keywords:
- IDebugProcessEx2::Attach method
ms.assetid: f3334ed7-39bf-4d02-a338-36f567b9b287
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0a39f674744d0b1e97e815d33c2d9564f4a39c0d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698607"
---
# <a name="idebugprocessex2attach"></a>IDebugProcessEx2::Attach
此方法将通知过程会话现在正在调试的进程。

## <a name="syntax"></a>语法

```cpp
HRESULT Attach( 
   IDebugSession2* pSession
);
```

```csharp
int Attach(
   IDebugSession2 pSession
);
```

#### <a name="parameters"></a>参数
 `pSession`

 [in]一个值，唯一标识附加到此进程的会话。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 接口传入`pSession`仅视为 cookie 中，用于唯一标识会话调试管理器附加到此进程; 的值上提供的接口的方法不起作用。

## <a name="see-also"></a>请参阅
- [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)