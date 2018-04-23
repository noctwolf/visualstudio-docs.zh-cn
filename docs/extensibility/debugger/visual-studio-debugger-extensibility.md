---
title: Visual Studio 调试器扩展性 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Debugging SDK
- Debugging SDK
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e5bb01c093fda068dfbc7dfa705914a8bdef4d2b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="visual-studio-debugger-extensibility"></a>Visual Studio 调试器扩展性
Visual Studio 包含一个完整交互式源代码调试器，为跟踪程序中的 bug 提供功能强大且易于使用的工具。 调试器具有完整的支持 Visual Basic、 C#、 C/c + + 和 JavaScript。 但是，对于[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]，即从可用[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=214453)，可以在相同的丰富功能的调试器支持其他编程语言。  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试器是常见的前端 （即，用户界面），接下来，特定于语言正在调试的调试组件。 对新语言，所有所需的支持通过[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试器是创建必要的后端组件，例如调试引擎 (DE)。 这正是[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]传入。  
  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]包括所有的完整参考[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]创建新 DE 所需的元素。 此外，还有示例和教程，可帮助你入门。  
  
 具有调试支持的语言项目系统的端到端示例，请参阅[IronPython 示例](http://msdn.microsoft.com/en-us/4c41695c-12c1-4670-b43b-d8d84c9e4089)。  
  
 下列各节描述如何使用扩展调试器[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
 [入门](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)  
 描述什么[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试产品/服务和如何安装 SDK。  
  
 [创建自定义调试引擎](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 记录 DE 自定义过程中，从断开 DE DE 准备你的程序。  
  
 [编写 CLR 表达式计算器](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
 说明是否必须编写的表达式计算器。  
  
 [选择调试引擎实施策略](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md)  
 讨论如何实现你 DE。  
  
 [参考](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md)  
 文档[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试 API。  
  
 [示例](../../extensibility/debugger/visual-studio-debugging-samples.md)  
 包含公共语言运行时表达式计算器示例和调试引擎示例的链接。
