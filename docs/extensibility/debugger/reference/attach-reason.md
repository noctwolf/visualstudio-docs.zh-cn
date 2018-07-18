---
title: ATTACH_REASON |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2dc7736f9210ef15cec8cece45d7899cc116a334
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099517"
---
# <a name="attachreason"></a>ATTACH_REASON
指定的调试引擎 (DE) 若要将附加到程序节点的原因。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
typedef DWORD ATTACH_REASON;  
```  
  
```csharp  
public enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
```  
  
## <a name="members"></a>成员  
 ATTACH_REASON_AUTO  
 将附加，因为进程当前处于调试模式。  
  
 ATTACH_REASON_LAUNCH  
 将附加，因为进程已启动。  
  
 ATTACH_REASON_USER  
 由于用户请求附加。  
  
## <a name="remarks"></a>备注  
 作为参数传递给使用这些值[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)和[附加](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [附加](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)