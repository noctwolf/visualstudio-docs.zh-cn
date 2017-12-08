---
title: "Visual Studio 中的解决方案和项目| Microsoft Docs"
ms.custom: 
ms.date: 10/5/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.addnewsolutionitem
- vs.environment.projects
- vs.openproject
- vs.addnewitem
- vs.addexistingitem
- VS.SolutionExplorer
- vs.newproject
- vs.addexistingsolutionitem
- vs.environment.solutions
- VS.SolutionExplorer.Solutions
helpviewer_keywords:
- solution items, folder in Solution Explorer
- solution items, shared
- solutions [Visual Studio]
- project items [Visual Studio], about project items
- solutions [Visual Studio], designing
- projects [Visual Studio]
- solutions [Visual Studio], projects and
- projects [Visual Studio], setting up
ms.assetid: aeaf56cb-c2dd-47f6-b012-23b84b7a7254
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ca3094b3bfe35381236798164fa18e58304bae3f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="solutions-and-projects-in-visual-studio"></a>Visual Studio 中的解决方案和项目
在 Visual Studio 中创建应用、网站、插件等时，会从项目开始。 在逻辑意义上，项目包含所有源代码文件、图标、图像、数据文件以及将编译到可执行程序或网站中，或是执行编译所需的任何其他内容。 项目还包含所有编译器设置以及程序将与之通信的各种服务或组件需要的其他配置文件。  

> [!NOTE]
>  如果不想则无需使用解决方案或项目。 只需在 Visual Studio 中打开文件并开始编辑代码。 请参阅[在 Visual Studio 中开发代码而无需创建项目或解决方案](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)了解详细信息。  

项目文件（.vbproj、.csproj、.vcxproj）是定义虚拟文件夹层次结构以及项目中所有项的路径的一种 XML 文件。 它还包含生成设置。 要查看项目文件中的内容，可以在解决方案资源管理器中选择项目名称，然后在上下文（右键单击）菜单中选择“卸载项目”。 然后，再次打开上下文菜单，依次选择“编辑”、“项目名称”**\<\>**。  

在 Visual Studio 中，项目文件由解决方案资源管理器用于显示项目内容和设置。 编译项目时，MSBuild 引擎会使用项目文件创建可执行文件。 还可以自定义项目以生成其他类型的输出。  

在逻辑意义上和文件系统中，项目包含在解决方案中，后者可能包含一个或多个相关项目，以及生成信息、Visual Studio 窗口设置和不与特定项目关联的任何杂项文件。 解决方案由格式唯一的文本文件 (.sln) 描述；它通常不应进行手动编辑。  

解决方案具有关联的 *.suo 文件，该文件为处理过项目的每个用户存储设置、首选项和配置信息。  

 下图显示项目与解决方案，以及它们在逻辑上包含的项之间的关系。  

 ![Visual Studio 项目和解决方案](../ide/media/vside-project-diagram.png)  

## <a name="creating-new-projects"></a>创建新项目  
 创建新项目的最简单方法是从项目模板开始，该模板由一组基本的预生成代码文件、配置文件、资产和设置组成，这些内容使你可以开始采用特定编程语言创建特定类型的应用程序或网站。 依次选择“文件”、“新建”、“项目”或“文件”、“新建”、“网站”后，“新建项目”或“新建网站”对话框会显示这些模板。 有关详细信息，请参阅[创建解决方案和项目](../ide/creating-solutions-and-projects.md)。  

还可以创建自定义项目和项模板。 有关详细信息，请参阅[创建项目和项模板](../ide/creating-project-and-item-templates.md)。  

## <a name="managing-projects-in-solution-explorer"></a>在解决方案资源管理器中管理项目  
 创建新项目之后，可使用 **“解决方案资源管理器”** 查看和管理项目和解决方案及其关联项。 下图显示具有一个包含两个项目的 C# 解决方案的解决方案资源管理器。  

 ![解决方案资源管理器](../ide/media/vs2015_solution_explorer.png "vs2015_solution_explorer")  

## <a name="in-this-section"></a>本节内容  

-   [创建解决方案和项目](../ide/creating-solutions-and-projects.md)  

-   [添加和移除项目项](../ide/adding-and-removing-project-items.md)  

-   [管理项目和解决方案属性](../ide/managing-project-and-solution-properties.md)  

-   [管理项目中的引用](../ide/managing-references-in-a-project.md)  

-   [应用程序属性](../ide/application-properties.md)  

-   [管理程序集和清单签名](../ide/managing-assembly-and-manifest-signing.md)  

-   [如何：指定应用程序图标（Visual Basic、C#）](../ide/how-to-specify-an-application-icon-visual-basic-csharp.md)  

-   [面向特定的 .NET Framework 版本](../ide/targeting-a-specific-dotnet-framework-version.md)  

-   [创建项目和项模板](../ide/creating-project-and-item-templates.md)  

## <a name="see-also"></a>另请参阅  
 [Visual Studio IDE](../ide/visual-studio-ide.md)
