---
title: 扩展调试器的路线图 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], roadmap
- Debugging SDK, roadmap
ms.assetid: 1f4096a8-f7aa-4dfa-84e1-6d59263e70bb
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 753f63b1a3deae2b1eab7bd46d1302bebaa16b85
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477418"
---
# <a name="roadmap-for-extending-the-debugger"></a>扩展调试器的路线图
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[扩展调试器的路线图](https://docs.microsoft.com/visualstudio/extensibility/debugger/roadmap-for-extending-the-debugger)。  
  
本文档提供了指南和参考信息，用于扩展[!INCLUDE[vs_current_short](../../includes/vs-current-short-md.md)]调试器与[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)]。  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 调试文档包括示例、 全面参考和几个有代表性的方案，展示了自定义调试器的典型方法。  
  
 你的编译器和其输出确定需要执行的操作实现在您的产品中进行调试。 如果您的编译器：  
  
-   面向 Windows 本机操作系统和写入。PDB 文件中，您可以使用本机代码调试引擎 (DE)，其集成到调试的程序[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。 不需要实现 DE 或表达式计算器。 表达式计算器是针对 c + + 编程语言的语法编写的。  
  
-   生成的 Microsoft 中间语言 (MSIL) 输出，可以通过托管的代码调试引擎 DE，这也集成到调试程序[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。 因此，只需实现的表达式计算器。 示例表达式计算器会为您提供。 有关详细信息，请参阅下列主题：  
  
     [表达式计算](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)  
  
     [计算表达式](../../extensibility/debugger/evaluating-expressions.md)  
  
     [表达式计算上下文](../../extensibility/debugger/expression-evaluation-context.md)  
  
     [中断模式中的表达式计算](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
     [编写公共语言运行时表达式计算器](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
  
-   一个专有操作系统或某些其他运行时环境的目标，您需要编写您自己 DE。 提供创建简单的部署使用 ATL COM 的教程。 有关详细信息，请参阅下列主题：  
  
     [创建自定义调试引擎](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
  
     [教程： 构建使用 ATL COM 的调试引擎](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24)  
  
     [实现端口提供程序](../../extensibility/debugger/implementing-a-port-supplier.md)  
  
     [示例](../../extensibility/debugger/visual-studio-debugging-samples.md)  
  
## <a name="see-also"></a>请参阅  
 [入门](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)

