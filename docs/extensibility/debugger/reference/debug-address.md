---
title: DEBUG_ADDRESS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_ADDRESS
helpviewer_keywords:
- DEBUG_ADDRESS structure
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d45fa0be28fcad891366581e13425d3940a0a967
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684606"
---
# <a name="debugaddress"></a>DEBUG_ADDRESS
此结构表示地址。

## <a name="syntax"></a>语法

```cpp
typedef struct _tagDEBUG_ADDRESS {
    ULONG32             ulAppDomainID;
    GUID                guidModule;
    _mdToken            tokClass;
    DEBUG_ADDRESS_UNION addr;
} DEBUG_ADDRESS;
```

```csharp
public struct DEBUG_ADDRESS {
    public uint                ulAppDomainID;
    public Guid                guidModule;
    public int                 tokClass;
    public DEBUG_ADDRESS_UNION addr;
}
```

## <a name="terms"></a>术语
ulAppDomainID 进程 id。

guidModule 包含此地址的模块的 GUID。

tokClass 确定类或此地址的类型的令牌。

> [!NOTE]
> 此值是特定于符号提供程序，因此具有以外的其他任何常规含义为类类型的标识符。

一个 addr [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)结构，其中包含描述单个地址类型的结构的并集。 值`addr`。`dwKind` 来自[ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)枚举，其中介绍了如何解释并集。

## <a name="remarks"></a>备注
此结构传递给[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)要填充的方法。

**警告 [c + +]**

如果`addr.dwKind`是`ADDRESS_KIND_METADATA_LOCAL`; 如果`addr.addr.addrLocal.pLocal`不为空值，则必须调用`Release`上标记的指针：

```
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL && addr.addr.addrLocal.pLocal != NULL)
{
    addr.addr.addrLocal.pLocal->Release();
}
```

## <a name="requirements"></a>要求
标头： sh.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
- [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)
