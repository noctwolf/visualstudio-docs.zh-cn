---
title: "使用工作流设计器开发应用程序 |Microsoft 文档"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DefaultWorkflowDesigner
- DefaultWorkflowDesigner.UI
helpviewer_keywords:
- Visual Studio 2010 Workflow Designer [WFD], overview
- Workflow Designer [WFD]
- Visual Studio 2010 Workflow Designer [WFD]
- Workflow Designer [WFD], overview
ms.assetid: 4cd062b1-b496-4668-bbc1-ee85545e066d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 75a6fb6eef1f5e8e174607ac141646ab237dd285
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="developing-applications-with-the-workflow-designer"></a>使用工作流设计器开发应用程序

Windows 工作流设计器是可视化设计器和调试器，用于以图形构造和调试的[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]中的应用程序[!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)]承载于[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]开发环境。 它可用于通过使用模板和活动设计器来撰写复合工作流应用程序、活动库或 [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 服务。 有关工作流的详细信息，请参阅[Windows Workflow Foundation &#91;.NET Framework 4&#93;](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66)。

 下面是一些 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 的旧版本中没有，而在 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 的新版本中增加的新设计功能：

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 是使用 [!INCLUDE[avalon1](../workflow-designer/includes/avalon1_md.md)] 生成的。 这将改善活动设计器体验并提高大型和复杂工作流的性能。

-   现在可通过 [!INCLUDE[avalon2](../workflow-designer/includes/avalon2_md.md)] 来设计自定义活动，并且使用 XAML 和编程模型来创建活动设计器也得到了简化。

-   实现了一个 Flowchart 活动，因此可以使用熟悉的流程图建模样式使程序流直观显示。

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 有一个新的变量设计器，可用于在工作流中声明变量和指定变量的作用域，从而将这些变量绑定到活动。

-   在 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 中，创作 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 工作流中的 Visual Basic 表达式时，[!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 可提供完整的 IntelliSense 功能。

-   调试体验现在已延伸至 XAML，使您能在 XAML 工作流定义中设置断点并在运行时单步执行 XAML 代码，这提供类似于托管代码中的体验。

-   与以前的版本相比，在 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 之外重新承载 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 得到了极大的简化，现在只需要几行代码。

-   新<xref:System.Activities.Statements.Flowchart>活动并将其[流程图](../workflow-designer/flowchart-activity-designer.md)，可以使你使用熟悉的流程图建模样式的程序流直观显示。

-   消息传递活动得到了增强，可以编写完全声明性（无代码）的 [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 服务。

-   **添加服务引用...**功能允许你自动用于访问 Web 服务生成的活动。