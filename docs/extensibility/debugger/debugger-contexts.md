---
title: 调试器上下文 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8a9310512417ac0e24046a1b7bcc1fd92099fe98
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="debugger-contexts"></a>调试器上下文
在[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试，调试引擎 (DE) 同时的范围内操作几个不同的上下文，如下所示：  
  
-   代码的上下文，其中介绍了中的程序的执行流的当前位置。  
  
-   文档上下文或位置，其中介绍了源文档中的当前位置。  
  
-   表达式计算上下文，描述中的哪个表达式求值将发生的上下文。  
  
## <a name="in-this-section"></a>本节内容  
 [代码上下文](../../extensibility/debugger/code-context.md)  
 为当前的运行时体系结构中与非传统的语言，其中代码可能不表示的说明，但某些其他方式的程序的指令流中的地址讨论代码上下文。  
  
 [文档位置](../../extensibility/debugger/document-position.md)  
 定义在 Visual Studio 调试通过抽象的源文件所知道到 IDE 中的位置中的文档位置。  
  
 [文档上下文](../../extensibility/debugger/document-context.md)  
 讨论在 Visual Studio 调试相对于源文件所在的文档上下文表示。 此外讨论如何符号处理程序映射代码上下文到文档上下文。  
  
 [表达式计算上下文](../../extensibility/debugger/expression-evaluation-context.md)  
 提供有关 Visual Studio 中的表达式评估上下文信息。 例如，与堆栈帧关联的表达式计算上下文提供有关评估本地变量、 方法参数和类成员的上下文。  
  
## <a name="related-sections"></a>相关章节  
 [调试概念](../../extensibility/debugger/debugger-concepts.md)  
 描述调试的主要体系结构概念。  
  
 [调试组件](../../extensibility/debugger/debugger-components.md)  
 概述 Visual Studio 调试组件，包括调试引擎 (DE)、 表达式计算器 (EE) 和符号处理程序 (SH)。  
  
 [调试任务](../../extensibility/debugger/debugging-tasks.md)  
 包含指向不同的调试任务，如启动程序和计算表达式。