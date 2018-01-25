---
title: "在 Visual Studio 中组织模板 | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project templates [Visual Studio], locations
- item templates [Visual Studio], locations
- template locations [Visual Studio]
- Visual Studio templates, organizing
- templates [Visual Studio], organizing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c58bda5570be9cdb7fba7a8f90a282df7b7167a2
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>如何：查找和组织项目和项模板

必须将模板文件放置在 Visual Studio 能识别的位置，以使模板出现在“新建项目”和“添加新项”对话框中。 还可以在用户模板位置创建自定义子类别，类别显示在“新建项目”和“添加新项”对话框中。

## <a name="locate-templates"></a>查找模板

已安装的模板和用户模板存储在两个不同位置。

### <a name="user-templates"></a>用户模板

如果将包含 .vstemplate 文件的压缩 (.zip) 文件添加到用户模板目录，则“新建项目”或“添加新项”对话框中将显示该模板。 默认情况下，用户模板位于：

- %USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ProjectTemplates

- %USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates

例如，以下目录包含用于 C# 的用户项目模板：

   C:\Users\UserName\Documents\Visual Studio 2017\Templates\ProjectTemplates\Visual C#\

> [!TIP]
> 可在“工具” > “选项” > “项目和解决方案” > “位置”中为用户模板设置位置。

### <a name="installed-templates"></a>已安装的模板

默认情况下，随 Visual Studio 一起安装的模板位于：

- \\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\\*Programming Language*\\*Locale ID*

- \\*VisualStudioInstallationDirectory*\Common7\IDE\ProjectTemplates\\*Programming Language*\\*Locale ID*

例如，以下目录包含以英语表示的 Visual Basic 项模板 (LCID 1033)：

   C:\\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\VisualBasic\1033\

## <a name="organize-templates"></a>组织模板

“新建项目”和“添加新项”对话框中的类别反映存在于已安装模板位置和用户模板位置的目录结构。 通过向用户模板目录添加新文件夹，可将用户模板组织到其各自的类别中。 “新建项目”和“添加新项”对话框将反映出对用户模板类别所做的任何更改。

> [!NOTE]
> 不能在编程语言级别创建新类别。 只能在每种语言中创建新类别。

### <a name="to-create-new-user-project-template-categories"></a>若要创建新的用户项目模板类别

1. 在用户项目模板目录中的编程语言文件夹中创建一个文件夹。 例如，要为 C# 项目模板创建“HelloWorld”类别，请创建以下目录：

    \%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ProjectTemplates\Visual C#\HelloWorld\

1. 将此类别的所有模板放入新文件夹。

1. 在“文件”菜单上，选择“新建” > “项目”。

   “HelloWorld”类别出现在“已安装” > “Visual C#”下的“新建项目”对话框中。

### <a name="to-create-new-user-item-template-categories"></a>若要创建新的用户项模板类别

1. 在用户项模板目录中的编程语言文件夹中创建一个文件夹。 例如，要为 C# 项模板创建“HelloWorld”类别，请创建以下目录：

    \%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual C#\HelloWorld\

1. 将此类别的所有模板放入新文件夹。

1. 创建项目或打开现有项目。 然后，在“项目”菜单上选择“添加新项”。

   “HelloWorld”类别出现在“已安装” > “Visual C# 项”下的“添加新项”对话框中。

### <a name="display-templates-in-parent-categories"></a>在父类别中显示模板

可以通过使用 .vstemplate 文件中的 `NumberOfParentCategoriesToRollUp` 元素允许子类别中的模板显示在其父类别中。 对于项目模板和项模板，操作步骤相同。

#### <a name="to-display-templates-in-parent-categories"></a>在父类别中显示模板

1. 找到包含模板的 .zip 文件。

1. 解压缩 .zip 文件。

1. 在 Visual Studio 中打开 .vstemplate 文件。

1. 在 `TemplateData` 元素内，添加一个 `NumberOfParentCategoriesToRollUp` 元素。 例如，以下代码使模板在父类别中可见，但在更高层次结构中不可见。

    ```xml
    <TemplateData>
        ...
        <NumberOfParentCategoriesToRollUp>
            1
        </NumberOfParentCategoriesToRollUp>
        ...
    </TemplateData>
    ```

1. 保存并关闭 .vstemplate 文件。

1. 选择模板中的文件，右键单击所选文件，然后选择“发送至” > “压缩的文件夹（zip 格式）”。

   这些文件被压缩到一个 .zip 文件中。

1. 删除解压缩的模板文件和旧的 .zip 模板文件。

1. 将新的 .zip 文件放入曾容纳已删除 .zip 文件的目录。

## <a name="see-also"></a>请参阅

[自定义模板](../ide/customizing-project-and-item-templates.md)  
[Visual Studio 模板架构引用（扩展性）](../extensibility/visual-studio-template-schema-reference.md)  
[NumberOfParentCategoriesToRollUp（Visual Studio 模板）](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)  
[如何：创建项目模板](../ide/how-to-create-project-templates.md)  
[如何：创建项模板](../ide/how-to-create-item-templates.md)
