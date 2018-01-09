---
title: "如何：在 Visual Studio 中对模板进行故障排除 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1d78554f39be1fdf21c5bbcb4d0abf5cf691fce9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-troubleshoot-templates"></a>如何：对模板进行故障排除

如果模板在开发环境中无法加载，可以采用以下几种方法找出问题。

## <a name="validating-the-vstemplate-file"></a>验证 .vstemplate 文件

如果模板中的 .vstemplate 文件未遵循 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 模板架构，则“新建项目”对话框中可能不会显示该模板。

### <a name="to-validate-the-vstemplate-file"></a>验证 .vstemplate 文件

1.  找到包含模板的 .zip 文件。  

2.  解压缩 .zip 文件。  

3.  在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中的“文件”菜单上，单击“打开”，再单击“文件”。

4.  选择模板的 .vstemplate 文件，然后单击“打开”。  
  
5.  验证 .vstemplate 文件的 XML 是否遵循 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 模板架构。 有关 .vstemplate 架构的详细信息，请参阅 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)。  

    > [!NOTE]
    > 要在创作 .vstemplate 文件时获得 IntelliSense 支持，请将 `xmlns` 特性添加到 `VSTemplate` 元素，并为其赋值 http://schemas.microsoft.com/developer/vstemplate/2005。

6.  保存并关闭 .vstemplate 文件。  
  
7.  选择模板中包括的文件，右键单击，选择“发送到”，然后单击“压缩(zipped)文件夹”。 所选的文件被压缩到一个 .zip 文件中。  
  
8.  将新的 .zip 文件与旧的 .zip 文件放在同一目录中。  
  
9. 删除解压缩的模板文件和旧的 .zip 模板文件。

## <a name="monitoring-the-event-log"></a>监视事件日志

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 记录处理模板 .zip 文件时遇到的错误。 如果“新建项目”对话框中未按预期显示模板，可以使用“事件查看器”排查问题。

### <a name="to-locate-template-errors-in-event-viewer"></a>在“事件查看器”中查找模板错误

1.  在 Windows 中，单击“开始”，再单击“控制面板”，双击“管理工具”，再双击“事件查看器”。  
  
2.  在左窗格中单击“应用程序”。  
  
3.  查找“源”值为 `Visual Studio - VsTemplate` 的事件。  
  
4.  双击模板事件以查看错误。

## <a name="see-also"></a>请参阅

[自定义模板](../ide/customizing-project-and-item-templates.md)   
[创建项目和项模板](../ide/creating-project-and-item-templates.md)   
[Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)