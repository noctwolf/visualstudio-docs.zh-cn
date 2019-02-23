---
title: IDebugPointerObject::SetBytes |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::SetBytes
helpviewer_keywords:
- IDebugPointerObject::SetBytes method
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e54a7f38eed85ffe2757b373de1af59e1aaa126b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694721"
---
# <a name="idebugpointerobjectsetbytes"></a>IDebugPointerObject::SetBytes
设置指向一系列连续字节中的值。

## <a name="syntax"></a>语法

```cpp
HRESULT SetBytes( 
   DWORD  dwStart,
   DWORD  dwCount,
   BYTE*  pBytes,
   DWORD* pdwBytes
);
```

```csharp
int SetBytes(
   uint     dwStart,
   uint     dwCount,
   byte[]   pBytes,
   out uint pdwBytes
);
```

#### <a name="parameters"></a>参数
 `dwStart`

 [in]偏移量，以字节为单位，从一开始指向的对象。

 `dwCount`

 [in]要设置的字节数。

 `pBytes`

 [in]一个表示新值的字节数组。 此值存储到的对象，从给定的偏移量处开始。

 `pdwBytes`

 [out]返回实际设置的字节数。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 如果使用此方法的指针表示由此[IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)指向基元类型或基元类型 （即，可以通过简单的字节序列表示一个数组） 的简单数组。 这`IDebugPointerObject`对象不能为空引用 （它必须指向出现在内存中的地址）。

## <a name="see-also"></a>请参阅
- [GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)