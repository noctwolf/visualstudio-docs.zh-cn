---
title: 字符串长度限制 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, restrictions on string lengths
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f600ef47526c3b2d9e703781c8f20ddb563dcf4a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49206203"
---
# <a name="restrictions-on-string-lengths"></a>字符串长度限制
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

源控件插件 API 限制在各种不同的函数中使用的字符串的长度。  
  
## <a name="string-length-values"></a>字符串长度值  
  
|返回的常量|“值”|  
|--------------|-----------|  
|`SCC_NAME_LEN`|31|  
|`SCC_AUXLABEL_LEN`|31|  
|`SCC_USER_LEN`|31|  
|`SCC_PRJPATH_LEN`|300|  
  
> [!NOTE]
>  长度不包括终止`null`。 其他常量而不是"_LEN"的"大小) (_s"后缀与执行包含终止的空间`null`。  
  
|返回的常量|“值”|  
|--------------|-----------|  
|SCC_NAME_SIZE|32|  
|SCC_AUXLABEL_SIZE|32|  
|SCC_USER_SIZE|32|  
|SCC_PRJPATH_SIZE|301|  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件](../extensibility/source-control-plug-ins.md)

