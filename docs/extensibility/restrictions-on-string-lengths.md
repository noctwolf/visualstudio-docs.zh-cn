---
title: 字符串长度限制 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, restrictions on string lengths
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56a76e84c27684d422b6554b22c75d945df4e928
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="restrictions-on-string-lengths"></a>字符串长度限制
源控件插件 API 限制在各种函数中使用的字符串的长度。  
  
## <a name="string-length-values"></a>字符串长度值  
  
|返回的常量|值|  
|--------------|-----------|  
|`SCC_NAME_LEN`|31|  
|`SCC_AUXLABEL_LEN`|31|  
|`SCC_USER_LEN`|31|  
|`SCC_PRJPATH_LEN`|300|  
  
> [!NOTE]
>  长度不包括结尾的`null`。 替换为"_SIZE"后缀，而不是"_LEN"其他常量中确实包含终止空间`null`。  
  
|返回的常量|值|  
|--------------|-----------|  
|SCC_NAME_SIZE|32|  
|SCC_AUXLABEL_SIZE|32|  
|SCC_USER_SIZE|32|  
|SCC_PRJPATH_SIZE|301|  
  
## <a name="see-also"></a>另请参阅  
 [源代码管理插件](../extensibility/source-control-plug-ins.md)