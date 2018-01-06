---
title: "CONSTRUCTOR_ENUM |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CONSTRUCTOR_ENUM
helpviewer_keywords: CONSTRUCTOR_ENUM enumeration
ms.assetid: 6d335b2c-66bc-460c-a4a6-4f3f1b697c2c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 737b7bc5d71c33b1d148e0df7b6e7cac8c891e3a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="constructorenum"></a>CONSTRUCTOR_ENUM
选择不同类型的构造函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum ConstructorMatchOptions {   
   crAll       = 0,  
   crNonStatic = 1,  
   crStatic    = 2  
} CONSTRUCTOR_ENUM;  
```  
  
```csharp  
public enum ConstructorMatchOptions {   
   crAll       = 0,  
   crNonStatic = 1,  
   crStatic    = 2  
};  
```  
  
## <a name="members"></a>成员  
 crAll  
 选择所有构造函数。  
  
 crNonStatic  
 选择非静态构造函数。  
  
 crStatic  
 选择静态构造函数。  
  
## <a name="remarks"></a>备注  
 作为自变量传递[EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md)方法。  
  
## <a name="requirements"></a>惠?  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)