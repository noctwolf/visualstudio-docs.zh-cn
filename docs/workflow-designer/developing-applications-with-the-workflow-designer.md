---
title: 使用工作流设计器开发应用程序
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ecc9e42146bfa7de259551ff1c90d27201db5725
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970120"
---
# <a name="developing-applications-with-the-workflow-designer"></a>使用工作流设计器开发应用程序

Windows 工作流设计器是可视化设计器和调试器，用于以图形构造和调试 Windows Workflow Foundation (WF) 中的应用程序在 Visual Studio 2010 开发环境中承载的.NET Framework 4。 它可用于撰写复合工作流应用程序、 活动库时或通过使用模板和活动设计器的 Windows Communication Foundation (WCF) 服务。 有关工作流的详细信息，请参阅[Windows Workflow Foundation &#91;.NET Framework 4&#93;](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66)。

 以下是一些设置此新版本的脱离较旧版本的工作流设计器工作流设计器的新设计功能：

-   工作流设计器使用 Windows Presentation Foundation (WPF) 进行构建。 这将改善活动设计器体验并提高大型和复杂工作流的性能。

-   现在可通过 [!INCLUDE[avalon2](../workflow-designer/includes/avalon2_md.md)] 来设计自定义活动，并且使用 XAML 和编程模型来创建活动设计器也得到了简化。

-   实现了一个 Flowchart 活动，因此可以使用熟悉的流程图建模样式使程序流直观显示。

-   工作流设计器具有新变量设计器，您可以声明和作用域在工作流中的变量绑定到活动。

-   在 Visual Studio 2010 中，工作流设计器创作.NET Framework 4 工作流中的 Visual Basic 表达式时提供完整的 IntelliSense 功能。

-   调试体验现在已延伸至 XAML，使你能在 XAML 工作流定义中设置断点并在运行时单步执行 XAML 代码，这提供类似于托管代码中的体验。

-   重新承载工作流设计器在 Visual Studio 之外是极大地简化相对于以前的版本，现在只需要几行代码。

-   新<xref:System.Activities.Statements.Flowchart>活动并将其[流程图](../workflow-designer/flowchart-activity-designer.md)，可以使你使用熟悉的流程图建模样式的程序流直观显示。

-   消息传递活动得到了增强，从而可以编写完全声明性 （无代码） Windows Communication Foundation (WCF) 服务。

-   **添加服务引用...** 功能允许你自动用于访问 Web 服务生成的活动。