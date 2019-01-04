---
title: 目录状态代码枚举器 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a8d6a541415e42e8d35dc4f3ab814c89cf939beb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53927605"
---
# <a name="directory-status-code-enumerator"></a>目录状态代码枚举器
`SccDirStatus`枚举数包含命名的常量值用于指定源代码管理系统中的目录的状态。 此枚举由[SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)。 这是在源控件插件 API 版本 1.2 中引入的。  
  
## <a name="syntax"></a>语法  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## <a name="members"></a>成员  
 SCC_DIRSTATUS_INVALID  
 无法获取状态;不依赖于它。  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 目录不是源代码管理下。  
  
 SCC_DIRSTATUS_CONTROLLED  
 目录位于源控件下。  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 对此目录相对应的项目为空。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)