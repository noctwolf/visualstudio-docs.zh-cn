---
title: IDebugProgramNodeAttach2::OnAttach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4deb573ece9ed2678e617ee74772184d4327551a
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "65459028"
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
将附加到相关联的程序或将推迟到 attach 进程[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)方法。

## <a name="syntax"></a>语法

```cpp
HRESULT OnAttach(
   [in] REFGUID guidProgramId
);
```

```csharp
int OnAttach(
   ref Guid guidProgramId
};
```

## <a name="parameters"></a>参数
 `guidProgramId`\

 [in]`GUID`要分配给关联的程序。

## <a name="return-value"></a>返回值
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)不应调用方法。 否则，返回错误代码。

## <a name="remarks"></a>备注
 此方法之前调用在附加过程中，[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)调用方法。 `OnAttach`方法可以执行附加过程本身 (在这种情况下，此方法返回`S_FALSE`) 或推迟到附加过程`IDebugEngine2::Attach`方法 (`OnAttach`方法将返回`S_OK`)。 在既情况下，`OnAttach`方法可以设置`GUID`到正在调试的程序的给定`GUID`。

## <a name="see-also"></a>请参阅
- [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)
- [附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)