---
title: CANSTOP_REASON |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- CANSTOP_REASON
helpviewer_keywords:
- CANSTOP_REASON enumeration
ms.assetid: 6da944eb-36cd-4a8c-8d71-544c775cfcc1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4129839094b7f5cf9907f6b92fa11fe1847f5806
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49938807"
---
# <a name="canstopreason"></a>CANSTOP_REASON
用于确定程序可以停止在到达执行的特定点后执行。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
typedef DWORD CANSTOP_REASON;  
```  
  
```csharp  
public enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
```  
  
## <a name="members"></a>成员  
 CANSTOP_ENTRYPOINT  
 指定给定的程序的入口点。  
  
 CANSTOP_STEPIN  
 指定单步执行函数。  
  
## <a name="remarks"></a>备注  
 作为参数传递[GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)方法来确认与会话调试管理器 (SDM)，如果，则可以暂时停止或单步执行函数或方法后到达该程序的入口点。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)