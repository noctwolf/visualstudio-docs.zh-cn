---
title: MODULE_FLAGS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- MODULE_FLAGS
helpviewer_keywords:
- MODULE_FLAGS enumeration
ms.assetid: 0e555b42-b846-4dbb-812e-8e3d11c85b2d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a1082e2e0c1e0d85270b95d4793d1029bbbb79e2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53955641"
---
# <a name="moduleflags"></a>MODULE_FLAGS
用于描述模块。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_MODULE_FLAGS {   
   MODULE_FLAG_NONE        = 0x0000,  
   MODULE_FLAG_SYSTEM      = 0x0001,  
   MODULE_FLAG_SYMBOLS     = 0x0002,  
   MODULE_FLAG_64BIT       = 0x0004,  
   MODULE_FLAG_OPTIMIZED   = 0x0008,  
   MODULE_FLAG_UNOPTIMIZED = 0x0010  
};  
typedef DWORD MODULE_FLAGS;  
```  
  
```csharp  
public enum enum_MODULE_FLAGS {   
   MODULE_FLAG_NONE        = 0x0000,  
   MODULE_FLAG_SYSTEM      = 0x0001,  
   MODULE_FLAG_SYMBOLS     = 0x0002,  
   MODULE_FLAG_64BIT       = 0x0004,  
   MODULE_FLAG_OPTIMIZED   = 0x0008,  
   MODULE_FLAG_UNOPTIMIZED = 0x0010  
};  
```  
  
## <a name="members"></a>成员  
 MODULE_FLAG_NONE  
 指定没有模块。  
  
 MODULE_FLAG_SYSTEM  
 指定系统模块。  
  
 MODULE_FLAG_SYMBOLS  
 指定符号的模块。  
  
 MODULE_FLAG_64BIT  
 指定的 64 位模块。  
  
 MODULE_FLAG_OPTIMIZED  
 指定该模块已进行了优化。 此状态反映在**模块**窗口。  
  
 MODULE_FLAG_UNOPTIMIZED  
 指定该模块未经过优化。 此状态反映在**模块**窗口。 这是默认状态。  
  
## <a name="remarks"></a>备注  
 用于`m_dwModuleFlags`的成员[MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)结构。  
  
 可能的按位组合这些标志`OR`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)