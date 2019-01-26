---
title: 调试器可扩展性入门 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 902551df1ff58e6d970b760e684df9861aac6fb4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043175"
---
# <a name="get-started-with-debugger-extensibility"></a>开始使用调试器可扩展性
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]提供了您需要创建和自定义用于调试程序中的调试器组件的信息[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]环境。  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 调试已添加派生自上以前执行的测试的广泛可用性改进[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试器。 可以使用[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试单步执行的多语言应用程序，也可以实现实时上调试应用程序和多语言解决方案时编辑的变量。  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 调试是执行的进程外与正在调试的程序，因此在应用程序的进程空间中较少受侵入。 因此，它是更轻松地编写与调试器的交互的组件，而不会影响调试程序。  
  
 最大效用[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]，您应熟悉以下各项：  
  
- [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]集成的开发环境 (IDE)  
  
- C + + 编程语言  
  
- ATL COM  
  
## <a name="in-this-section"></a>本节内容  
 [扩展调试器的路线图](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 概述了实现在您的产品，具体取决于您的编译器和其输出中进行调试的过程。  
  
 [调试器组件](../../extensibility/debugger/debugger-components.md)  
 提供的概述[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]调试组件，包括调试引擎 (DE)、 表达式计算器 (EE) 和符号处理程序 (SH)。  
  
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)  
 描述调试的主要体系结构概念。  
  
 [调试器上下文](../../extensibility/debugger/debugger-contexts.md)  
 介绍了调试引擎 (DE) 的运行方式同时代码、 文档和表达式计算上下文中。 介绍的三个上下文、 位置、 位置或与它相关评估每个。  
  
 [调试任务](../../extensibility/debugger/debugging-tasks.md)  
 包含指向不同的调试任务，如启动程序和计算表达式。