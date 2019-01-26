---
title: PROGRAM_DESTROY_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- PROGRAM_DESTROY_FLAGS enumeration
ms.assetid: be00d4a3-d5b8-4159-b632-64577f534883
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5ba9bd2ae2ac7f06432495cf7d7b680ed1f98898
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029643"
---
# <a name="programdestroyflags"></a>PROGRAM_DESTROY_FLAGS
枚举有效的程序值销毁标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_PPROGRAM_DESTROY_FLAGS  
{  
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1  
};  
typedef DWORD PROGRAM_DESTROY_FLAGS;  
```  
  
```csharp  
public enum enum_PPROGRAM_DESTROY_FLAGS  
{  
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1  
};  
```  
  
## <a name="terms"></a>术语  
 PROGRAM_DESTROY_CONTINUE_DEBUGGING  
 销毁程序，但继续进行调试。  
  
## <a name="remarks"></a>备注  
 返回枚举[GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)方法。  
  
## <a name="requirements"></a>要求  
 标头：Msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)