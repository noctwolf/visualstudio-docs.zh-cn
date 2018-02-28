---
title: "PDB_TYPE |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PDB_TYPE
helpviewer_keywords:
- PDB_TYPE structure
ms.assetid: 1c1bb772-77d6-4870-90b2-fd9247d0004e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f1c08df8cf56d81ebb22fbdf17f3d20084599b51
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="pdbtype"></a>PDB_TYPE
此结构指定有关摘自 PDB 符号字段类型的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _tagTYPE_PDB {  
   ULONG32 ulAppDomainID;  
   GUID    guidModule;  
   DWORD   symid;  
} PDB_TYPE;  
```  
  
```csharp  
public struct PDB_TYPE {  
   public uint ulAppDomainID;  
   public Guid guidModule;  
   public uint symid;  
};  
```  
  
#### <a name="parameters"></a>参数  
 ulAppDomainID  
 符号源于应用程序 ID。 这用于唯一标识应用程序的实例。  
  
 guidModule  
 包含此字段的模块的 GUID。  
  
 symid  
 对应于此字段的符号 ID。  
  
## <a name="remarks"></a>备注  
 此结构显示为中的联合的一部分[TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)结构时`dwKind`字段`TYPE_INFO`结构设置为`TYPE_KIND_PDB`(从值[dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)枚举）。  
  
## <a name="requirements"></a>惠?  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)