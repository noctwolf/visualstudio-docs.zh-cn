---
title: BP_UNBOUND_REASON |Microsoft Docs
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
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 554bdd9def52cfbde5b4fe535f017f762f1c8edc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469256"
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[BP_UNBOUND_REASON](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-unbound-reason)。  
  
提供了一个断点是未绑定的原因。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
typedef DWORD BP_UNBOUND_REASON;  
```  
  
```csharp  
public enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
```  
  
## <a name="members"></a>成员  
 BPUR_UNKNOWN  
 原因是未知的。  
  
 BPUR_CODE_UNLOADED  
 包含断点的代码已被卸载。  
  
 BPUR_BREAKPOINT_REBIND  
 断点已重新绑定到另一个位置。 这可以进行编辑后，断点移，或者在该断点绑定到具有将不再有效的路径的文件时继续操作。  
  
 BPUR_ BREAKPOINT_ERROR  
 确定断点绑定后，要错误。 其条件不再有效的托管断点发生这种情况。  
  
## <a name="remarks"></a>备注  
 返回的[GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)

