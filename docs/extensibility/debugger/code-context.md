---
title: "代码上下文 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 97a4c8f8a9a710fab70760d9cb6eabb61de7a26f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="code-context"></a>代码上下文
在[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试，**代码上下文**:  
  
-   因为识别的调试引擎 (DE)，则提供的代码中的位置的抽象。 为大多数运行时体系结构现在，代码上下文可以看作的程序的指令流中的地址。 对于非传统的语言，其中代码不可能由说明来表示，则可以通过其他一些表示代码上下文。  
  
-   描述中被调试的程序的执行流的当前位置。  
  
-   存在仅当程序停止在断点处。  
  
-   具有关联的文档上下文。  
  
-   由实现[IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md)接口。  
  
## <a name="see-also"></a>请参阅  
 [文档上下文](../../extensibility/debugger/document-context.md)   
 [调试器上下文](../../extensibility/debugger/debugger-contexts.md)