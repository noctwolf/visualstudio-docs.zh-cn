---
title: 文档上下文 |Microsoft Docs
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
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c5753e2353b351f6aa4bd73c5aced3d4959b3cde
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51741195"
---
# <a name="document-context"></a>文档上下文
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

在中[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]调试**文档上下文**:  
  
-   表示源文件中的位置。 对于其中的源文件可能不存在的语言，文档上下文标识通常由运行时环境生成的文档中的位置。 例如，脚本引擎可能会从脚本生成文档。 有关详细信息，请参阅[文档位置](../../extensibility/debugger/document-position.md)。  
  
-   描述对应于代码上下文的源文档中的位置。 符号处理程序映射到文档上下文中，使用生成的编译器或解释器信息的代码上下文。  
  
-   由实现[IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md)接口。  
  
## <a name="see-also"></a>请参阅  
 [代码上下文](../../extensibility/debugger/code-context.md)   
 [符号提供程序](../../extensibility/debugger/symbol-provider.md)   
 [符号提供程序接口](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [调试器上下文](../../extensibility/debugger/debugger-contexts.md)

