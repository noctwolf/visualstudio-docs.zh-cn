---
title: "文档上下文 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b121259f9be23d235386d7156ca8d326c5847f87
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="document-context"></a>文档上下文
在[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试，**文档上下文**:  
  
-   表示在源文件中的位置。 对于其中的源文件可能不存在的语言，文档上下文标识通常由运行时环境生成的文档中的位置。 例如，脚本引擎可能从脚本生成一个文档。 有关详细信息，请参阅[文档位置](../../extensibility/debugger/document-position.md)。  
  
-   描述对应于代码上下文的源文档中的位置。 符号处理程序映射到文档的上下文中，使用信息由编译器或解释器生成的代码的上下文。  
  
-   由实现[IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md)接口。  
  
## <a name="see-also"></a>请参阅  
 [代码上下文](../../extensibility/debugger/code-context.md)   
 [符号提供程序](../../extensibility/debugger/symbol-provider.md)   
 [符号提供程序接口](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [调试器上下文](../../extensibility/debugger/debugger-contexts.md)