---
title: UNMANAGED_ADDRESS_THIS_RELATIVE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UNMANAGED_ADDRESS_THIS_RELATIVE
helpviewer_keywords:
- UNMANAGED_ADDRESS_THIS_RELATIVE structure
ms.assetid: e6a91ace-2d47-4ff9-aefb-8d8b68eab0b2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e9d2bf87a804295a5ea8f6750ee9cd93643c53bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913005"
---
# <a name="unmanagedaddressthisrelative"></a>UNMANAGED_ADDRESS_THIS_RELATIVE
此结构表示的地址是相对于`this`指针 (`Me`在 Visual Basic 中)。

## <a name="syntax"></a>语法

```cpp
typedef struct _tagUNMANAGED_THIS_RELATIVE {
   DWORD dwOffset;
   DWORD dwBitOffset;
   DWORD dwBitLength;
} UNMANAGED_ADDRESS_THIS_RELATIVE;
```

```csharp
public struct UNMANAGED_THIS_RELATIVE {
   public uint dwOffset;
   public uint dwBitOffset;
   public uint dwBitLength;
}
```

## <a name="terms"></a>术语
 dwOffset 字节偏移量从 （例如类 vtable 开始） 的基位置。

 dwBitOffset 偏移量中的基位置中的位 (始终为 0 除非引用的位字段)。

 dwBitLength 的位数表示的地址 (始终为 0 除非引用的位字段)。

## <a name="remarks"></a>备注
 此结构是中的联合的一部分[DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)结构时`dwKind`字段`DEBUG_ADDRESS_UNION`结构设置为`ADDRESS_KIND_UNMANAGED_THIS_RELATIVE`(从值[ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)枚举）。

## <a name="requirements"></a>要求
 标头： sh.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)