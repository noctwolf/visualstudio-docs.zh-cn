---
title: PARSEFLAGS |Microsoft Docs
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
- PARSEFLAGS
helpviewer_keywords:
- PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ccf50c5bd85ae6a69a24da3a3d830009e3297be8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483714"
---
# <a name="parseflags"></a>PARSEFLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[PARSEFLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/parseflags)。  
  
指定如何分析表达式。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
typedef DWORD PARSEFLAGS;  
```  
  
```csharp  
public enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
```  
  
## <a name="members"></a>成员  
 PARSE_EXPRESSION  
 指示该表达式不是一个语句。  
  
 PARSE_FUNCTION_AS_ADDRESS  
 指示表达式是以进行分析 （和更高版本评估） 地址。  
  
 PARSE_DESIGN_TIME_EXPR_EVAL  
 指示在设计时正在分析表达式 （即，设计器打开时）。  
  
## <a name="remarks"></a>备注  
 作为参数传递给[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)并[分析](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [分析](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)

