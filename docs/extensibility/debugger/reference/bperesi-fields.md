---
title: BPERESI_FIELDS |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2280740766e20a048f57e58590cc529d98b85264
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31110050"
---
# <a name="bperesifields"></a>BPERESI_FIELDS
指定要检索的断点了失败的解决方法有关的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD BPERESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>成员  
 PERESI_BPRESLOCATION  
 初始化/使用`bpResLocation`（断点解析位置） 字段[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)结构。  
  
 BPERESI_PROGRAM  
 初始化/使用`pProgram`字段`BP_ERROR_RESOLUTION_INFO`结构。  
  
 BPERESI_THREAD  
 初始化/使用`pThread`字段`BP_ERROR_RESOLUTION_INFO`结构。  
  
 BPERESI_MESSAGE  
 初始化/使用`bstrMessage`字段`BP_ERROR_RESOLUTION_INFO`结构。  
  
 BPERESI_TYPE  
 初始化/使用`dwType`（断点类型） 字段`BP_ERROR_RESOLUTION_INFO`结构。  
  
 BPERESI_ALLFIELDS  
 初始化/使用的所有字段`BP_ERROR_RESOLUTION_INFO`结构。  
  
## <a name="remarks"></a>备注  
 作为参数传递给传递[GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)方法，以指示哪些字段[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)结构是否被初始化。  
  
 这些值还用于指示中的哪些字段`BP_ERROR_RESOLUTION_INFO`结构均使用和有效时返回该结构。  
  
 这些值可以与按位组合`OR`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)