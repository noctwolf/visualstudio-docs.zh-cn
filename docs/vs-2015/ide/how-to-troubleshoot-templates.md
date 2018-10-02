---
title: 如何：进行模板的故障排除 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, troubleshooting
ms.assetid: 3e577ad2-f725-4c11-93b3-477f2404ec81
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b249fe28f91a8dfb24e73ab86f785103910ee9d9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478047"
---
# <a name="how-to-troubleshoot-templates"></a>如何：进行模板的故障排除
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 对进行故障排除模板](https://docs.microsoft.com/visualstudio/ide/how-to-troubleshoot-templates)。  
  
如果模板在开发环境中无法加载，可以采用以下几种方法找出问题。  
  
## <a name="validating-the-vstemplate-file"></a>验证 .vstemplate 文件  
 如果模板中的 .vstemplate 文件未遵循 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 模板架构，则“新建项目”对话框中可能不会显示该模板。  
  
#### <a name="to-validate-the-vstemplate-file"></a>验证 .vstemplate 文件  
  
1.  找到包含模板的 .zip 文件。  
  
2.  解压缩 .zip 文件。  
  
3.  在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中的“文件”菜单上，单击“打开”，再单击“文件”。  
  
4.  选择模板的 .vstemplate 文件，然后单击“打开”。  
  
5.  验证 .vstemplate 文件的 XML 是否遵循 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 模板架构。 有关 .vstemplate 架构的详细信息，请参阅 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)。  
  
    > [!NOTE]
    >  若要获取在创作.vstemplate 文件时 IntelliSense 支持，请添加`xmlns`归于`VSTemplate`元素并将其分配的值为 http://schemas.microsoft.com/developer/vstemplate/2005。  
  
6.  保存并关闭 .vstemplate 文件。  
  
7.  选择模板中包括的文件，右键单击，选择“发送到”，然后单击“压缩(zipped)文件夹”。 所选的文件被压缩到一个 .zip 文件中。  
  
8.  将新的 .zip 文件与旧的 .zip 文件放在同一目录中。  
  
9. 删除解压缩的模板文件和旧的 .zip 模板文件。  
  
## <a name="monitoring-the-event-log"></a>监视事件日志  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 记录处理模板 .zip 文件时遇到的错误。 如果“新建项目”对话框中未按预期显示模板，可以使用“事件查看器”排查问题。  
  
#### <a name="to-locate-template-errors-in-event-viewer"></a>在“事件查看器”中查找模板错误  
  
1.  在 Windows 中，单击“开始”，再单击“控制面板”，双击“管理工具”，再双击“事件查看器”。  
  
2.  在左窗格中单击“应用程序”。  
  
3.  查找“源”值为 `Visual Studio - VsTemplate` 的事件。  
  
4.  双击模板事件以查看错误。  
  
## <a name="see-also"></a>请参阅  
 [自定义模板](../ide/customizing-project-and-item-templates.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)



