---
title: m_stateObject 字段 |Microsoft Docs
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
- m_stateObject field, Task class [.NET Framework debug engines]
ms.assetid: 68c54b22-3e1c-4031-b9c7-b972c519d8a0
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3231f63d91e8393e5fa1417d97202d1b46cdd571
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51732368"
---
# <a name="mstateobject-field"></a>m_stateObject 字段
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

一个对象，表示该操作将使用的数据。  
  
 **Namespace**：<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （在 mscorlib.dll 中)  
  
 无法从.NET Framework 来访问此内部成员，因为以下语法提供通用中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.field assembly object m_stateObject  
```  
  
## <a name="remarks"></a>备注  
 这是`state`中的参数<xref:System.Threading.Tasks.Task.%23ctor%2A>构造函数。 它也是为支持字段<xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=fullName>属性。  
  
## <a name="see-also"></a>请参阅  
 [Task 类](../../extensibility/debugger/task-class-internal-members.md)

