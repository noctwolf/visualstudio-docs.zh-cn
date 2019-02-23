---
title: FIELD_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FIELD_INFO
helpviewer_keywords:
- FIELD_INFO structure
ms.assetid: bfafef6d-0c83-43d7-a779-1f0d24b166a1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 83cdacae192ad1286203139432a0eacd632b8511
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694221"
---
# <a name="fieldinfo"></a>FIELD_INFO
此结构描述本地变量、 参数或其他字段。

## <a name="syntax"></a>语法

```cpp
typedef struct _tagFieldInfo {
    FIELD_INFO_FIELDS dwFields;
    BSTR              bstrFullName;
    BSTR              bstrName;
    BSTR              bstrType;
    FIELD_MODIFIERS   dwModifiers;
} FIELD_INFO;
```

```csharp
public struct FIELD_INFO {
    public uint   dwFields;
    public string bstrFullName;
    public string bstrName;
    public string bstrType;
    public uint   dwModifiers;
};
```

## <a name="members"></a>成员
dwFields A 中的标志的组合[FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md)枚举，用于指定哪些成员已填写。

bstrFullName 字段的完整名称。

bstrName 字段的短名称。

bstrType 字段的类型。

dwModifiers A 中的标志的组合[FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)描述字段的枚举。

## <a name="remarks"></a>备注
此结构传递给[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)填写其中的方法。

## <a name="requirements"></a>要求
标头： sh.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)
- [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md)
- [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)
