---
title: m_stateObject 字段 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- m_stateObject field, Task class [.NET Framework debug engines]
ms.assetid: 68c54b22-3e1c-4031-b9c7-b972c519d8a0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 79313460d380b2b505f6fa75f35351811ddaa470
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31097454"
---
# <a name="mstateobject-field"></a>m_stateObject 字段
一个表示操作将使用的数据的对象。  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （mscorlib.dll) 中  
  
 由于无法访问此内部成员在.NET Framework 中，以下语法提供共同点中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.field assembly object m_stateObject  
```  
  
## <a name="remarks"></a>备注  
 这是`state`中的参数<xref:System.Threading.Tasks.Task.%23ctor%2A>构造函数。 它也是供后备字段<xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=fullName>属性。  
  
## <a name="see-also"></a>另请参阅  
 [任务类](../../extensibility/debugger/task-class-internal-members.md)