---
title: CODE_PATH |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CODE_PATH
helpviewer_keywords:
- CODE_PATH structure
ms.assetid: 2d4b2890-4c9d-47e1-83c0-df9c6436427f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 474b239159fbd6e5e35588837e9e5c65deb11b03
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49180058"
---
# <a name="codepath"></a>CODE_PATH
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

介绍的方法或函数调用。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
typedef struct tagCODE_PATH {   
   BSTR                bstrName;  
   IDebugCodeContext2* pCode;  
} CODE_PATH;  
```  
  
```csharp  
public struct CODE_PATH {  
   public string            bstrName;  
   public IDebugCodeContext pCode;  
}  
```  
  
## <a name="members"></a>成员  
 bstrName  
 代码路径的名称。  
  
 pCode  
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)单步执行函数代码中何处标识的对象。  
  
## <a name="remarks"></a>备注  
 此结构用于实现单步执行函数。 [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)返回从当前正在调试的程序中的位置的所有调用。 此结构表示一个此类调用。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)

