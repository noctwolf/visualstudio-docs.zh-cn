---
title: ADDRESS_KIND |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- ADDRESS_KIND
helpviewer_keywords:
- ADDRESS_KIND enumeration
ms.assetid: 3a12fbec-7088-4cf9-8f6f-ad8ddec6009a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 53c93cb8e7d2c021c95c4b11047b5d699f7ae1c4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="addresskind"></a>ADDRESS_KIND
指定类型的地址。  
  
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
 ADDRESS_KIND_NATIVE  
 表示本机地址[NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md)结构。  
  
 ADDRESS_KIND_UNMANAGED_THIS_RELATIVE  
 相对于非托管的地址`this`(`Me`在 Visual Basic 中) 指针，将由[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md)结构。  
  
 ADDRESS_KIND_UNMANAGED_PHYSICAL  
 非托管的物理地址，由表示[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md)结构。  
  
 ADDRESS_KIND_METHOD  
 类，由表示的方法[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md)结构。  
  
 ADDRESS_KIND_FIELD  
 类，由表示的字段[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md)结构。  
  
 ADDRESS_KIND_LOCAL  
 地址个本地变量和由[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md)结构。  
  
 ADDRESS_KIND_PARAM  
 一个方法或函数的参数，由表示[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md)结构。  
  
 ADDRESS_KIND_ARRAYELEM  
 数组元素，由表示[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md)结构。  
  
 ADDRESS_KIND_RETVAL  
 返回值，由表示[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md)结构。  
  
## <a name="remarks"></a>备注  
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)方法返回[DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)结构，其中包含的可能结构的联合[DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)结构。 `dwKind`字段`DEBUG_ADDRESS_UNION`结构保留`ADDRESS_KIND`值并介绍了如何解释联合的字段。  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)