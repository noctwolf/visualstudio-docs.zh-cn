---
title: m_children 字段 |Microsoft Docs
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
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a681f3a58fddbb136383a1259aa5e4c0c3b96b69
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49289622"
---
# <a name="mchildren-field"></a>m_children 字段
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

使用此任务中注册的子任务的列表。  
  
 **Namespace**：<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （在 mscorlib.dll 中)  
  
 无法从.NET Framework 来访问此内部成员，因为以下语法提供通用中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>备注  
 运行任务时，只有执行任务的线程应访问此数组。  
  
 如果完成此任务，其他线程可以访问此字段，只要它们不要向其添加任何内容或从其中删除任何内容。  
  
## <a name="see-also"></a>请参阅  
 [ContingentProperties 类](../../extensibility/debugger/contingentproperties-class-internal-members.md)

