---
title: ATTACH_REASON |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a59e0c8b0d29529af068b3f0e2aec5f605b7e015
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471723"
---
# <a name="attachreason"></a>ATTACH_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[ATTACH_REASON](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/attach-reason)。  
  
指定调试引擎 (DE) 的原因，若要将附加到程序节点。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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
 将附加，因为启动进程。  
  
 ATTACH_REASON_USER  
 由于用户请求而将附加。  
  
## <a name="remarks"></a>备注  
 这些值用作参数[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)并[附加](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [附加](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)

