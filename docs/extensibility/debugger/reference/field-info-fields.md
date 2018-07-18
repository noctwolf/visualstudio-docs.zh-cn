---
title: FIELD_INFO_FIELDS |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- FIELD_INFO_FIELDS
helpviewer_keywords:
- FIELD_INFO_FIELDS enumeration
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d74f39ce8e9e350c791371f20b7401d685fb1d18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102488"
---
# <a name="fieldinfofields"></a>FIELD_INFO_FIELDS
指定要检索有关的信息[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_FIELD_INFO_FIELDS {   
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
typedef DWORD FIELD_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_FIELD_INFO_FIELDS {  
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
```  
  
## <a name="members"></a>成员  
 FIF_FULLNAME  
 初始化/使用`bstrFullName`字段[FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)结构。  
  
 FIF_NAME  
 初始化/使用`bstrName`字段`FIELD_INFO`结构。  
  
 FIF_TYPE  
 初始化/使用`bstrType`字段`FIELD_INFO`结构。  
  
 FIF_MODIFIERS  
 初始化/使用`bstrModifiers`字段`FIELD_INFO`结构。  
  
## <a name="remarks"></a>备注  
 这些值还会传递的自变量作为[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)方法，以指定的哪些字段[FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)结构是否被初始化。  
  
 这些值也用在`dwFields`的成员`FIELD_INFO`结构以指示哪些字段是使用和有效。  
  
 这些标志可以与按位组合`OR`。  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)