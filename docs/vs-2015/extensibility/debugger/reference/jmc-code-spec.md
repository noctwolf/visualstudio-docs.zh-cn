---
title: JMC_CODE_SPEC |Microsoft Docs
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
- JMC_CODE_SPEC
helpviewer_keywords:
- JMC_CODE_SPEC structure
ms.assetid: d89498f1-4234-46d9-b4e2-abbcbca5068a
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6c7b723da4093e46d07910c2579f9602e0fa99e0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481915"
---
# <a name="jmccodespec"></a>JMC_CODE_SPEC
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[JMC_CODE_SPEC](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/jmc-code-spec)。  
  
此结构用于设置模块的 JustMyCode 信息。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
typedef struct _JMC_CODE_SPEC {  
   BOOL fIsUserCode;  
   BSTR bstrModuleName;  
} JMC_CODE_SPEC;  
```  
  
```csharp  
public struct JMC_CODE_SPEC {  
   public int    fIsUserCode;  
   public string bstrModuleName;  
};  
```  
  
## <a name="members"></a>成员  
 fIsUserCode  
 非零 (`TRUE`) 如果该模块将被视为用户代码; 否则为零 (`FALSE`) 如果模块是被视为外部代码而不进行调试。  
  
 bstrModuleName  
 相关模块的名称。  
  
## <a name="remarks"></a>备注  
 此结构传递到此类结构的列表作为[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)

