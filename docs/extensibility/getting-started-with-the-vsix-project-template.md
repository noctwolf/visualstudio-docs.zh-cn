---
title: VSIX 项目模板入门 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, VSIX project template
ms.assetid: 89fac33e-9380-4723-9b45-048a6e16f0ed
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 28aa6c6e2b7aca671b1f1ac9d9be7f34261b867b
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39499434"
---
# <a name="get-started-with-the-vsix-project-template"></a>开始使用 VSIX 项目模板
若要创建扩展或包部署的现有扩展，可以使用 VSIX 项目模板。 VSIX 项目模板具有 Visual Basic 和 Visual C# 版本中，并在 Visual Studio SDK 的一部分安装。  
  
 VSIX 项目模板中只包含的*source.extension.vsixmanifest*文件，其中包含有关扩展和资产发布时附带的信息。  
  
 若要查找 VSIX 项目模板，必须安装 Visual Studio SDK。 有关详细信息，请参阅[Visual Studio SDK](../extensibility/visual-studio-sdk.md)。  
  
## <a name="deploy-a-custom-project-template-using-the-vsix-project-template"></a>部署自定义项目模板使用 VSIX 项目模板  
 以下步骤演示如何使用 VSIX 项目打包可以与其他开发人员共享，也可以将上传到 Visual Studio 库的项目模板。  
  
1.  创建项目模板。  
  
    1.  打开从其创建模板的项目。 此项目可以是任何项目类型。  
  
    2.  在“项目”菜单上，单击“导出模板”。 完成该向导的步骤。  
  
         一个 *.zip*中创建文件 *%USERPROFILE%\My Documents\Visual Studio\<版本 > \My Exported Templates\\*。  
  
2.  创建一个空的 VSIX 项目。  
  
     在 **文件** 菜单上，单击 **新建** ，然后单击 **项目**。 选择任一**Visual Basic**或**Visual C#**。 在所选节点下，选择**扩展性**，然后选择**VSIX 项目**。  
  
3.  添加 *.zip*到项目文件。 设置其**复制到输出目录**属性设置为`Copy Always`。  
  
4.  在中**解决方案资源管理器**，双击*source.extension.vsixmanifest*文件中打开**VSIX 清单设计器**，然后进行以下更改：  
  
    -   设置**产品名称**字段**我的项目模板**。  
  
    -   设置**产品 ID**字段**MyProjectTemplate-1**。  
  
    -   设置**作者**字段**Fabrikam**。  
  
    -   设置**描述**字段**我的项目模板**。  
  
    -   在中**资产**部分中，添加**Microsoft.VisualStudio.ProjectTemplate**类型，并将其路径设置为的名称 *.zip*文件。  
  
5.  保存并关闭*source.extension.vsixmanifest*文件。  
  
6.  生成项目。  
  
7.  在输出目录中，双击 *.vsix*文件。  
  
8.  一个**VSIX 安装程序**会显示消息框。 按照说明安装扩展。  
  
9. 关闭 Visual Studio，然后重新打开它。  
  
10. 选择**扩展和更新**(在**工具**菜单)，然后选择**模板**类别。 其中一个可用的扩展应为**我的项目模板**。  
  
11. 新的项目模板中显示**新的项目**原始项目模板的同一位置中的对话框。 例如，如果创建一个名为模板**VB 控制台**从 Visual Basic 控制台应用程序**VB 控制台**将显示在 Visual Basic 中为同一窗格**控制台应用程序**模板。  
  
### <a name="to-specify-the-location-of-the-template-in-the-new-project-dialog-box"></a>若要在新建项目对话框框中指定模板的位置  
  
1.  模板文件夹位于 *{Visual Studio 安装路径} \Common7\IDE\ProjectTemplates*和 * {Visual Studio 安装路径} \Common7\IDE\ItemTemplates} 目录。 顶部的名称级别中的部分**新的项目**对话框不完全匹配的模板文件夹的名称。 如果它们不同，使用模板文件夹的名称。  
  
     更改 *.vsix*文件扩展名为 *.zip*，然后打开该文件。  
  
2.  创建具有相同的名称的一部分的新文件夹**新的项目**中应会显示该模板的对话框。  
  
3.  如果模板将出现在一个子节中，创建具有相同名称的子文件夹。  
  
4.  将模板移 *.zip*到新文件夹的文件。  
  
5.  更改 *.zip*扩展 *.vsix*。  
  
6.  打开 VSIX 清单。  
  
7.  在 VSIX 清单中，更新**资产**模板使其指向包含该模板文件的目录树的根的路径。 例如，如果模板处于*\CSharp\Windows*，该引用应指向*\CSharp*。