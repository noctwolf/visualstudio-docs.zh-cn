---
title: IDebugProgramHost2::GetHostId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramHost2::GetHostId
helpviewer_keywords:
- IDebugProgramHost2::GetHostId
ms.assetid: 7702e221-feb1-446b-a224-cb46c420987e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fa7f8e20ed41b753447d49653e49c8096b8bc114
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203989"
---
# <a name="idebugprogramhost2gethostid"></a>IDebugProgramHost2::GetHostId
获取承载此程序的进程的进程标识符。

## <a name="syntax"></a>语法

```cpp
HRESULT GetHostId( 
   AD_PROCESS_ID* pdwId
);
```

```csharp
int GetHostId( 
   AD_PROCESS_ID[] pdwId
);
```

## <a name="parameters"></a>参数
`pdwId`\
[in、 out][AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)使用的进程标识符信息填充的结构。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)