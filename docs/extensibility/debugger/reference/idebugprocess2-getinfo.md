---
title: IDebugProcess2::GetInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetInfo
helpviewer_keywords:
- IDebugProcess2::GetInfo
ms.assetid: 46021dce-bb97-46c3-b0cc-e5b3b68acc35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d2a3b8b1ef028562502454994da18e799b8f28b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62871091"
---
# <a name="idebugprocess2getinfo"></a>IDebugProcess2::GetInfo
获取过程的说明。

## <a name="syntax"></a>语法

```cpp
HRESULT GetInfo(
   PROCESS_INFO_FIELDS  Fields,
   PROCESS_INFO*        pProcessInfo
);
```

```csharp
int GetInfo(
   enum_PROCESS_INFO_FIELDS  Fields,
   PROCESS_INFO[]            pProcessInfo
);
```

#### <a name="parameters"></a>参数
 `Fields`

 [in]中值的组合[PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)枚举，用于指定的哪些字段`pProcessInfo`参数是要填充。

 `pProcessInfo`

 [out]一个[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)填充过程的描述的结构。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)
- [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)