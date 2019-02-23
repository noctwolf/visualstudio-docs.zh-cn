---
title: BP_COND_STYLE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 70ab3655d27e810b3c05d0e0e81d81bc15a26950
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685854"
---
# <a name="bpcondstyle"></a>BP_COND_STYLE
指定断点条件的样式的挂起和绑定断点。

## <a name="syntax"></a>语法

```cpp
enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
typedef DWORD BP_COND_STYLE;
```

```csharp
public enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
```

## <a name="members"></a>成员
BP_COND_NONE 触发断点时达到断点的位置。 没有指定断点条件。

BP_COND_WHEN_TRUE 触发断点仅在条件表达式时与断点关联的计算结果为`true`。

BP_COND_WHEN_CHANGED 触发断点仅在与断点关联的条件表达式的值时已从其以前的评估。

## <a name="remarks"></a>备注
用于`styleCondition`的成员[BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)结构。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
