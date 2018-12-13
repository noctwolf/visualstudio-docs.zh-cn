---
title: 如何： 更新现有模板 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: aa7c6f534756298006e07d287b118edfd4944717
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49242269"
---
# <a name="how-to-update-existing-templates"></a>如何：更新现有模板
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

创建模板并将文件压缩为一个 .zip 文件后，你可能想要修改该模板。 可以通过以下两种方式完成此操作，即手动更改模板中的文件，或者从基于该模板的项目中导出新模板。  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>使用“导出模板”向导更新现有模板  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 提供了**导出模板**可用于更新现有模板的向导。  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>使用“导出模板”更新现有模板  
  
1.  在 **文件** 菜单上，单击 **新建** ，然后单击 **新建项目**。  
  
2.  选择你想要更新，输入名称和位置为临时项目，然后单击模板**确定**。  
  
3.  在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中修改项目。  
  
4.  上**文件**菜单上，单击**将模板导出**，并使用**将模板导出**向导以创建新的模板。  
  
5.  在将更新的模板压缩为 .zip 文件后，请删除旧的 .zip 模板文件。  
  
## <a name="manually-updating-an-existing-template"></a>手动更新现有模板  
 通过修改压缩的 .zip 文件中的文件，可以在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 之外更新现有模板。  
  
#### <a name="to-manually-update-an-existing-template"></a>手动更新现有模板  
  
1.  找到包含模板的 .zip 文件。 默认情况下，此文件位于 documents\visual Studio*版本*\My Exported Templates\\。  
  
2.  解压缩 .zip 文件。  
  
3.  修改或删除当前的模板文件，或向该模板添加新文件。  
  
4.  打开、修改并保存 .vstemplate XML 文件，以处理已更新的行为或新文件。 有关 .vstemplate 架构的详细信息，请参阅 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)。 有关什么参数化在源文件中的详细信息，请参阅[模板参数](../ide/template-parameters.md)  
  
5.  选择的文件在模板中，右键单击，单击**发送到**，然后单击**压缩 (zipped) 文件夹**。 所选的文件被压缩到一个 .zip 文件中。  
  
6.  将新 .zip 文件放在旧 .zip 文件的同一目录中。  
  
7.  删除解压缩的模板文件和旧的 .zip 模板文件。  
  
8.  启动 （以管理员身份） 实例的开发人员命令提示 (开始菜单下**Visual Studio 2010 / Visual Studio 工具/开发人员命令提示**)。  
  
9. 运行以下命令：`devenv /installvstemplates`。  
  
## <a name="see-also"></a>请参阅  
 [自定义模板](../ide/customizing-project-and-item-templates.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [模板参数](../ide/template-parameters.md)   
 [如何：创建初学者工具包](../ide/how-to-create-starter-kits.md)



