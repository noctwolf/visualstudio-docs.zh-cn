---
title: "MODULE_INFO_FLAGS |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MODULE_INFO_FLAGS
helpviewer_keywords: MODULE_INFO_FLAGS enumeration
ms.assetid: e22d3723-b4d4-4524-8a2f-3adb55bbd273
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 052ea8dd40254e3c5d852e3fc95722d185c08239
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="moduleinfoflags"></a>MODULE_INFO_FLAGS
指定用于模块的符号的状态。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_MODULE_INFO_FLAGS {  
   MIF_SYMBOLS_LOADED = 0x0001  
};  
typedef DWORD MODULE_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_MODULE_INFO_FLAGS {  
   MIF_SYMBOLS_LOADED = 0x0001  
};  
```  
  
## <a name="members"></a>成员  
 MIF_SYMBOLS_LOADED  
 至少一个组的符号加载的模块 （否则已加载任何符号）。  
  
## <a name="remarks"></a>备注  
 此值由返回[GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)方法。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)