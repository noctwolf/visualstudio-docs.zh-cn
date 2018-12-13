---
title: CONTEXT_INFO_FIELDS |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CONTEXT_INFO_FIELDS
helpviewer_keywords:
- CONTEXT_INFO_FIELDS enumeration
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5169ff103b823067d64c58a3f6223220f67a3d52
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51734224"
---
# <a name="contextinfofields"></a>CONTEXT_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定要检索有关内存上下文信息。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum enum_CONTEXT_INFO_FIELDS {   
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
typedef DWORD CONTEXT_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_CONTEXT_INFO_FIELDS {  
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
```  
  
## <a name="members"></a>成员  
 CIF_MODULEURL  
 初始化/用`bstrModuleUrl`字段[CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)结构。  
  
 CIF_FUNCTION  
 初始化/用`bstrFunction`字段的`CONTEXT_INFO`结构。  
  
 CIF_FUNCTIONOFFSET  
 初始化/用`posFunctionOffset`字段的`CONTEXT_INFO`结构。  
  
 CIF_ADDRESS  
 初始化/用`bstrAddress`字段的`CONTEXT_INFO`结构。  
  
 CIF_ADDRESSOFFSET  
 初始化/用`bstrAddressOffset`字段的`CONTEXT_INFO`结构。  
  
 CIF_ALLFIELDS  
 初始化/使用的所有字段`CONTEXT_INFO`结构。  
  
## <a name="remarks"></a>备注  
 这些值会传递的参数[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)方法，以指示的哪些字段[CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)结构是进行初始化。  
  
 这些标志还用于指示哪些字段的`CONTEXT_INFO`结构已使用且有效时返回该结构。  
  
 可能会使用按位 OR 组合这些值。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)

