---
title: "用于项目和文件的 Visual Studio 模板| Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [Visual Studio], project
- templates [Visual Studio], item
- item templates [Visual Studio]
- project templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3959b01fdfc0ff77bdd5a3ffa0c96366b9da87d7
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="project-and-item-templates"></a>项目和项模板

项目和项目模板提供了可重用的存根，为用户提供了一些基本代码和结构，以供其根据自己的用途进行自定义。

## <a name="visual-studio-templates"></a>Visual Studio 模板

一系列预定义的项目和项模板会随 Visual Studio 一并安装。 例如，“新建项目”对话框中显示的 Visual Basic 和 C#“Windows 窗体应用”和“类库”模板是项目模板。 项模板显示在“添加新项”对话框中，并包含代码文件、XML 文件、HTML 页和样式表等项。

这些模板为用户提供一个开始创建项目或扩展现有项目的起点。 项目模板提供特定项目类型所需的文件，包括标准程序集引用，并设置默认项目属性和编译器选项。 项模板的复杂程度不一，从具有某个文件扩展名的单个空文件到包含具有存根代码的源代码文件、设计器信息文件和嵌入资源等的多文件项。

除了“新建项目”和“添加新项”对话框中的已安装模板，还可以创作自己的模板或下载并使用社区创建的模板。 有关详细信息，请参阅[如何：创建项目模板](../ide/how-to-create-project-templates.md)和[如何：创建项模板](../ide/how-to-create-item-templates.md)。

## <a name="contents-of-a-template"></a>模板的内容

所有项目模板和项模板（无论是与 Visual Studio 一起安装的还是由你创建的）均通过使用相同的原则工作并具有类似的内容。 所有模板均包含以下项：

- 使用模板时要创建的文件。 包括源代码文件、嵌入资源、项目文件等。

- 一个 vstemplate 文件。 该文件包含元数据，元数据提供在“新建项目”和“添加新项”对话框中显示模板以及从模板创建项目或项时所需的信息。 有关 .vstemplate 文件的详细信息，请参阅[模板参数](../ide/template-parameters.md)。

当这些文件压缩成 .zip 文件并放在正确的文件夹时，Visual Studio 将自动在以下位置显示这些文件：

- “新建项目”对话框中显示项目模板。

- “添加新项”对话框中显示项模板。

有关模板文件夹的详细信息，请参阅[如何：查找和组织模板](../ide/how-to-locate-and-organize-project-and-item-templates.md)。

## <a name="starter-kits"></a>初学者工具包

初学者工具包是增强的模板，可与社区的其他成员共享。 初学者工具包包含可编译的代码示例、文档及其他资源，这些资源可帮助用户在生成有用的实际应用程序的同时学习新工具和编程技巧。 初学者工具包的基本内容和流程与模板的一样。 有关详细信息，请参阅[如何：创建初学者工具包](../ide/how-to-create-starter-kits.md)。

## <a name="see-also"></a>请参阅

[如何：创建项目模板](../ide/how-to-create-project-templates.md)  
[如何：创建项模板](../ide/how-to-create-item-templates.md)  
[模板参数](../ide/template-parameters.md)  
[自定义模板](../ide/customizing-project-and-item-templates.md)  
[Visual Studio 模板中的 NuGet 包](/nuget/visual-studio-extensibility/visual-studio-templates)