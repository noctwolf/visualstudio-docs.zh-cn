---
title: NATIVE_ADDRESS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- NATIVE_ADDRESS
helpviewer_keywords:
- NATIVE_ADDRESS structure
ms.assetid: 7a0cd085-bfc8-45cc-a3d4-4459070e207a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ec086080aa01b1c362321f3d5add248f8ece8ea7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53901949"
---
# <a name="nativeaddress"></a>NATIVE_ADDRESS
此结构表示本机地址。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _tagNATIVE_ADDRESS {  
   DWORD unknown;  
} NATIVE_ADDRESS;  
```  
  
```csharp  
public struct NATIVE_ADDRESS {  
   public uint unknown;  
}  
```  
  
## <a name="terms"></a>术语  
 未知  
 （这其中的含义取决于运行时和操作系统） 本机地址。  
  
## <a name="remarks"></a>备注  
 此结构是中的联合的一部分[DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)结构时`dwKind`字段`DEBUG_ADDRESS_UNION`结构设置为`ADDRESS_KIND_NATIVE`(从值[ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)枚举）。  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)