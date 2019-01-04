---
title: SEEK_START |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SEEK_START
helpviewer_keywords:
- SEEK_START enumeration
ms.assetid: 55bd8901-626e-428b-a263-23b14417f4c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6aa97560982b49f4544589b18b72892c683d24e7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53850513"
---
# <a name="seekstart"></a>SEEK_START
指定从其开始反汇编流中查找的位置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
typedef DWORD SEEK_START;  
```  
  
```csharp  
public enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
```  
  
## <a name="members"></a>成员  
 SEEK_START_BEGIN  
 查找当前文档的开始处启动。  
  
 SEEK_START_END  
 查找当前文档结尾处启动。  
  
 SEEK_START_CURRENT  
 查找在当前文档的当前位置开始。  
  
 SEEK_START_CODECONTEXT  
 启动查找在当前文档的给定的代码上下文。  
  
 SEEK_START_CODELOCID  
 启动查找给定的代码的位置标识符。 代码位置标识符获取通过调用[GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)。  
  
## <a name="remarks"></a>备注  
 作为参数传递[Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [查找](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)   
 [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)