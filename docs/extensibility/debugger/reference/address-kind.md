---
title: ADDRESS_KIND | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ADDRESS_KIND
helpviewer_keywords:
- ADDRESS_KIND enumeration
ms.assetid: 3a12fbec-7088-4cf9-8f6f-ad8ddec6009a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 71888e4e0b339b9b9b94946e8d9c49f8ffb1f84c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56696815"
---
# <a name="addresskind"></a>ADDRESS_KIND
指定地址的类型。

## <a name="syntax"></a>语法

```cpp
enum enum_ADDRESS_KIND {
    ADDRESS_KIND_NATIVE                  = 0x0001,
    ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,
    ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,
    ADDRESS_KIND_METADATA_METHOD         = 0x0010,
    ADDRESS_KIND_METADATA_FIELD          = 0x0011,
    ADDRESS_KIND_METADATA_LOCAL          = 0x0012,
    ADDRESS_KIND_METADATA_PARAM          = 0x0013,
    ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,
    ADDRESS_KIND_METADATA_RETVAL         = 0x0015,
};
typedef DWORD ADDRESS_KIND;
```

```csharp
public enum enum_ADDRESS_KIND {
    ADDRESS_KIND_NATIVE                  = 0x0001,
    ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,
    ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,
    ADDRESS_KIND_METADATA_METHOD         = 0x0010,
    ADDRESS_KIND_METADATA_FIELD          = 0x0011,
    ADDRESS_KIND_METADATA_LOCAL          = 0x0012,
    ADDRESS_KIND_METADATA_PARAM          = 0x0013,
    ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,
    ADDRESS_KIND_METADATA_RETVAL         = 0x0015,
};
```

## <a name="terms"></a>术语
ADDRESS_KIND_NATIVE 的本机通讯，由此[NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md)结构。

相对于非托管地址 ADDRESS_KIND_UNMANAGED_THIS_RELATIVE `this` (`Me`在 Visual Basic 中) 指针，由[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md)结构。

ADDRESS_KIND_UNMANAGED_PHYSICAL 的非托管的物理地址，由此[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md)结构。

ADDRESS_KIND_METHOD 一个方法的类，表示[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md)结构。

ADDRESS_KIND_FIELD 一个字段的类，表示[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md)结构。

ADDRESS_KIND_LOCAL 的地址是本地变量和为由[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md)结构。

ADDRESS_KIND_PARAM 方法或函数参数，表示[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md)结构。

ADDRESS_KIND_ARRAYELEM 数组元素，表示[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md)结构。

ADDRESS_KIND_RETVAL 一个返回值，表示[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md)结构。

## <a name="remarks"></a>备注
[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)方法将返回[DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)结构，其中包含的可能结构、 联合[DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)结构。 `dwKind`字段`DEBUG_ADDRESS_UNION`结构保存`ADDRESS_KIND`值并介绍了如何解释联合字段。

## <a name="requirements"></a>要求
标头： sh.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)
- [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
