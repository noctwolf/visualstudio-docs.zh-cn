---
title: BUILT_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BUILT_TYPE
helpviewer_keywords:
- BUILT_TYPE structure
ms.assetid: cc02c32c-0f65-4210-ad25-a9b1899066e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 09f0438bed235729d390b784725b89abec201c7f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693517"
---
# <a name="builttype"></a>BUILT_TYPE
此结构指定从元数据字段类型有关的信息。

## <a name="syntax"></a>语法

```cpp
typedef struct _tagTYPE_BUILT {
    ULONG32      ulAppDomainID;
    GUID         guidModule;
    IDebugField* pUnderlyingField;
} BUILT_TYPE;
```

```csharp
public struct BUILT_TYPE {
    public uint        ulAppDomainID;
    public Guid        guidModule;
    public IDebugField pUnderlyingField;
};
```

#### <a name="parameters"></a>参数
ulAppDomainID 符号所来自的应用程序 ID。 这用于唯一标识应用程序的实例。

guidModule 模块包含此字段的 GUID。

pUnderlyingField [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)标识与此生成的字段关联的基础字段对象。

## <a name="remarks"></a>备注
此结构显示为中的联合的一部分[TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)结构时`dwKind`字段`TYPE_INFO`结构设置为`TYPE_KIND_BUILT`(从值[dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)枚举）。

## <a name="requirements"></a>要求
标头： sh.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
