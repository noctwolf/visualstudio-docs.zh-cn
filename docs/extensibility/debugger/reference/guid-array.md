---
title: GUID_ARRAY | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eed39ee4446e66e1e7b1700d97ad680eb62c2523
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704964"
---
# <a name="guidarray"></a>GUID_ARRAY
介绍可用的调试引擎的唯一标识符的数组。

## <a name="syntax"></a>语法

```cpp
typedef struct tagGUID_ARRAY
{
    DWORD dwCount;
    GUID *Members;
} GUID_ARRAY;
```

```csharp
public struct GUID_ARRAY
{
    public uint dwCount;
    public Guid Members;
}
```

## <a name="terms"></a>术语
dwCount 数组中的唯一标识符的数量。

成员数组，其中包含唯一标识符。

## <a name="remarks"></a>备注
返回此结构[GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)方法。

## <a name="requirements"></a>要求
标头：Msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)
