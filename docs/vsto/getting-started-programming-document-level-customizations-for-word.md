---
title: 要开始使用 word 的文档级自定义项编程
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word solutions in Visual Studio
- Word projects [Office development in Visual Studio], getting started
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a5bed5c08e15861840a34960d186b408fb86085d
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2018
ms.locfileid: "34448849"
---
# <a name="get-started-programming-document-level-customizations-for-word"></a>要开始使用 word 的文档级自定义项编程
  如果你刚开始使用 Visual Studio 创建 Microsoft Office Word 的文档级自定义项，下面是你需要知道。  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
## <a name="understand-how-document-level-customizations-for-word-work"></a>了解如何使用文档级自定义 Word 工作项  
 基于您创建每个 Word 自定义的是单个文档。 若要开始使用自定义项，最终用户打开文档或从 Word 模板中创建文档。 在文档中，例如将光标移动到特定区域或单击按钮和菜单项的事件可以在程序集中调用事件处理方法。 当文档关闭时，提供自定义项的功能将不再在 Word 中可用。  
  
 有关详细信息，请参阅[的文档级自定义项的体系结构](../vsto/architecture-of-document-level-customizations.md)。  
  
## <a name="create-document-level-projects-for-word"></a>创建 Word 文档级项目  
 若要创建 Word 的文档级自定义项，使用中的 Word 文档或 Word 模板项目模板**新项目**对话框。 这些模板包括所需程序集引用和项目文件。  
  
 有关如何创建 Word 的文档级项目的详细信息，请参阅[如何： 在 Visual Studio 中的创建 Office 项目](../vsto/how-to-create-office-projects-in-visual-studio.md)。 有关项目模板的详细信息，请参阅[Office 项目模板概述](../vsto/office-project-templates-overview.md)。  
  
## <a name="program-word-documents-by-using-host-items-host-controls"></a>使用主机项主机控件的程序 Word 文档  
 *主机项*和*宿主控件*是提供用于文档级自定义项编程模型的类。  
  
 主机项提供的入口点为你的代码，并且它们还可以充当主机控件和 Windows 窗体控件的容器。 在 word 文档级项目中，主机项都由`ThisDocument`类。  
  
 主机控件基于本机 Word 对象，例如内容控件、 书签、 和 XML 节点。 宿主控件提供了类似功能的本机 Word 对象，但它们还具有新的事件、 设计器支持和数据绑定功能。 它们显示为在你的项目代码并在 IntelliSense 中，它可以轻松而无需导航 Word 对象模型引用在代码中直接的特定对象的第一类对象。  
  
 有关详细信息，请参阅下列主题：  
  
-   [文档级自定义项进行编程](../vsto/programming-document-level-customizations.md)  
  
-   [通过使用扩展的对象自动化 Word](../vsto/automating-word-by-using-extended-objects.md)  
  
-   [主机项和主机控件概述](../vsto/host-items-and-host-controls-overview.md)  
  
## <a name="customize-the-user-interface-of-word"></a>自定义 Word 的用户界面  
 大多数 Microsoft Office 解决方案的 Office 应用程序提供用户与解决方案交互某种方式修改的用户界面 (UI)。 有多种方法使用的文档级自定义项可以在其中修改 Word 的 UI。 例如，可以将控件添加到功能区中，并可以显示操作窗格。 有关详细信息，请参阅[Office UI 自定义](../vsto/office-ui-customization.md)。  
  
 你也可以打开与你直接在 Visual Studio 中的项目相关联的文档。 在 Visual Studio 中打开文档时，你可以通过使用 Word 用户界面来修改文档。 此外可以作为设计界面，可用于将控件拖放到它上面使用的文档。 有关详细信息，请参阅[Visual Studio 环境中的 Office 项目](../vsto/office-projects-in-the-visual-studio-environment.md)。  
  
## <a name="bind-controls-to-data"></a>将控件绑定到数据  
 内容控件和<xref:Microsoft.Office.Tools.Word.Bookmark>控件是在列表中，你可以从拖动控件**数据源**窗口。 添加内容控件和创建一个书签，在此方式自动将将它们绑定到使用窗口设置数据源。 无需编写任何代码，可以显示来自数据库、 服务和业务对象数据。 有关详细信息，请参阅[将数据绑定到 Office 解决方案中的控件](../vsto/binding-data-to-controls-in-office-solutions.md)。  
  
## <a name="next-steps"></a>后续步骤  
 若要了解如何创建 Word 的文档级自定义项，请参阅[演练： 创建你的第一个文档级自定义 word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)。 本演练向你介绍 Visual Studio 和 Word 文档级自定义项的编程模型中的 Office 开发工具。  
  
 有关指导你完成一些 Word 项目中的常见任务的主题的列表，请参阅[Office 编程中的常见任务](../vsto/common-tasks-in-office-programming.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何： 在 Visual Studio 中创建 Office 项目](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [文档级自定义项进行编程](../vsto/programming-document-level-customizations.md)   
 [Word 解决方案](../vsto/word-solutions.md)   
 [演练： 创建你的第一个文档级自定义 word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)   
 [使用 Word 的演练](../vsto/walkthroughs-using-word.md)   
 [Word 对象模型概述](../vsto/word-object-model-overview.md)   
 [在 Office 解决方案中编写代码](../vsto/writing-code-in-office-solutions.md)  
  
  