---
title: "DEBUG_ADDRESS |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEBUG_ADDRESS
helpviewer_keywords:
- DEBUG_ADDRESS structure
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1985fcf51e6d5ce02cf582257f5a3a142334faf1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
 ulAppDomainID  
 进程 id。  
  
 guidModule  
 包含此地址的模块的 GUID。  
  
 tokClass  
 确定类或的此地址的类型标记。  
  
> [!NOTE]
>  此值特定于符号提供程序，并因此具有以外的其他任何常规含义与类类型的标识符。  
  
 Addr  
 A [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)结构，其中包含描述单个地址类型的结构的并集。 值`addr`。`dwKind` 来自[ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)枚举，说明如何解释联合。  
  
## <a name="remarks"></a>备注  
 此结构传递给[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)方法填充的。  
  
 **警告 [c + +]**  
  
 如果`addr.dwKind`是`ADDRESS_KIND_METADATA_LOCAL`如果`addr.addr.addrLocal.pLocal`不是 null 值，则必须调用`Release`令牌指针上：  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>惠?  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)