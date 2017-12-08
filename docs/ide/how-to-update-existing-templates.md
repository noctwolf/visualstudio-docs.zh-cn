---
title: "如何：更新现有模板 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0fffcc55953e394c5efd00b86949f04474a66111
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-update-existing-templates"></a>如何：更新现有模板
创建模板并将文件压缩为一个 .zip 文件后，你可能想要修改该模板。 可以通过以下两种方式完成此操作，即手动更改模板中的文件，或者从基于该模板的项目中导出新模板。  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>使用“导出模板”向导更新现有模板  
Visual Studio 提供了“导出模板”向导，该向导可用于更新现有模板。  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>使用“导出模板”更新现有模板  
  
1.  通过选择“文件”、“新建”、“项目”来打开“新建项目”对话框。  
  
2.  选择要更新的模板，输入项目的名称和位置，然后选择“确定”。  
  
3.  修改 Visual Studio 中的项目。  
  
4.  在“项目”菜单上，选择“导出模板”。  

    “导出模板向导”随即打开。  

5.  按照向导中的提示将模板以 .zip 文件导出。  

6.  删除旧的模板 .zip 文件。  
  
## <a name="manually-updating-an-existing-template"></a>手动更新现有模板  
通过修改压缩的 .zip 文件中的文件，可在 Visual Studio 之外更新现有模板。  
  
#### <a name="to-manually-update-an-existing-template"></a>手动更新现有模板  
  
1.  找到包含模板的 .zip 文件。 默认情况下，此文件位于 %USERPROFILE%\Documents\Visual Studio \<version\>\My Exported Templates\.  
  
2.  解压缩 .zip 文件。  
  
3.  修改或删除当前的模板文件，或向该模板添加新文件。  
  
4.  打开、修改并保存 .vstemplate XML 文件，以处理已更新的行为或新文件。  

    有关 .vstemplate 架构的详细信息，请参阅 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)。 有关可在源文件中进行参数化的内容的详细信息，请参阅[模板参数](../ide/template-parameters.md)。  
  
5.  选择模板中的文件，右键单击，选择“发送至”，然后选择“压缩文件夹”。  

    所选的文件被压缩到一个 .zip 文件中。  
  
6.  将新 .zip 文件放在旧 .zip 文件的同一目录中。  
  
7.  删除解压缩的模板文件和旧的 .zip 模板文件。  
  
8.  启动开发人员命令提示符的提升实例：  

  1. 在“开始”菜单中，导航到“Visual Studio \<version\>”、“开发人员命令提示符”。  

  2. 从上下文（右键单击）菜单中，依次选择“更多”、“以管理员身份运行”。  
  
9. 运行以下命令：`devenv /installvstemplates`。  
  
## <a name="see-also"></a>请参阅  
[自定义模板](../ide/customizing-project-and-item-templates.md)   
[创建项目和项模板](../ide/creating-project-and-item-templates.md)   
[Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
[模板参数](../ide/template-parameters.md)   
[如何：创建初学者工具包](../ide/how-to-create-starter-kits.md)