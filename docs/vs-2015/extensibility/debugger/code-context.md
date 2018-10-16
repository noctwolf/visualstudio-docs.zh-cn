---
title: 代码上下文 |Microsoft Docs
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
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 88bdd673de5ef8d8339dabf1c19618ea8e3faa44
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49215574"
---
# <a name="code-context"></a>代码上下文
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

在中[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]调试**代码上下文**:  
  
-   已知的调试引擎 (DE) 提供了代码中的位置的抽象。 为大多数运行时体系结构现在，代码上下文可以认为的程序的指令流中的地址。 对于非传统的语言，其中介绍了如何不可能表示代码，可以通过某些其他方法来表示代码上下文。  
  
-   描述正在调试的程序的执行流中的当前位置。  
  
-   存在仅当程序停止在断点处。  
  
-   将具有关联的文档上下文。  
  
-   由实现[IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md)接口。  
  
## <a name="see-also"></a>请参阅  
 [文档上下文](../../extensibility/debugger/document-context.md)   
 [调试器上下文](../../extensibility/debugger/debugger-contexts.md)

