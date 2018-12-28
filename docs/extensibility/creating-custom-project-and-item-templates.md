---
title: 创建自定义项目和项模板 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9e4d938bbfbe1c65882e73630689edff208670e9
ms.sourcegitcommit: 159ed9d4f56cdc1dff2fd19d9dffafe77e46cd4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2018
ms.locfileid: "53739820"
---
# <a name="create-custom-project-and-item-templates"></a>创建自定义项目和项模板

Visual Studio SDK 的项目模板可创建自定义项目模板和自定义项模板。 这些模板包括一些常见的参数替换项，并以 zip 文件形式生成。 它们不会自动部署，且它们不支持的实验实例中。 必须将生成的 zip 文件复制到用户模板目录。

模板创建模板，可以包括在更大的扩展的模板。 这样可以实现上的源文件的版本控制和生成到一个 VSIX 包的一组模板项目。

此外可以配置要安装 NuGet 包的模板。 有关详细信息，请参阅[Visual Studio 模板中的 NuGet 包](/nuget/visual-studio-extensibility/visual-studio-templates)。

对于基本模板创建方案，应使用**导出模板**向导，将输出到压缩的文件。 有关创建基本模板的详细信息，请参阅[创建项目和项模板](../ide/creating-project-and-item-templates.md)。

> [!NOTE]
> 从 Visual Studio 2017 中，扫描自定义项目和项模板将无法再执行。 相反，该扩展插件必须提供模板清单文件描述这些模板的安装位置。 Visual Studio 2017 可用于更新您的 VSIX 扩展。 如果部署使用 MSI 扩展，则必须手动生成模板清单文件。 有关详细信息，请参阅[Visual Studio 2017 升级自定义项目和项模板](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md)。 模板清单架构记录在[Visual Studio 模板清单架构参考](../extensibility/visual-studio-template-manifest-schema-reference.md)。

## <a name="create-a-project-template"></a>创建项目模板

1.  创建项目模板项目。 您可以发现中的项目模板**新的项目**对话框中的，在 Visual Basic 或 Visual C#*扩展性*文件夹。

     该模板会生成一个类文件，一个图标 *.vstemplate*文件，名为一个可编辑项目文件*ProjectTemplate.vbproj*或*ProjectTemplate.csproj*，和一些文件通常都由其他项目类型，此类*resources.resx*文件中， *AssemblyInfo*文件，和一个 *.settings*文件。 每个代码文件包含常见的参数替换在适当的位置。

2.  添加和删除项目所需的项目中的项。 不删除可编辑项目文件中， *AssemblyInfo*文件，或 *.vstemplate*文件。

3.  更新 *.vstemplate*文件以反映任何添加和删除操作。 [项目](../extensibility/project-element-visual-studio-templates.md)元素必须包含[ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)每个文件要包含在模板中的元素。

4.  修改代码文件和其他面向用户的内容，并添加适当的参数替换项。

5.  修改根据需要生成的内容。

6.  生成项目。

     Visual Studio 将创建 *.zip*文件，其中包含你的模板。 未部署，并且不可用的实验实例中。

## <a name="create-an-item-template"></a>创建项模板

1.  创建项模板项目。

     该模板会生成一个类文件，一个图标 *.vstemplate*文件，和一个*AssemblyInfo*文件。 类文件包含一些常见的参数替换。

2.  添加和删除项目所需的项目中的项。

3.  更新 *.vstemplate*文件以反映任何添加和删除操作。 [项目](../extensibility/project-element-visual-studio-templates.md)元素必须包含[ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)每个文件要包含在模板中的元素。

4.  修改代码文件和其他面向用户的内容，并添加适当的参数替换项。

5.  修改生成所需的内容。

6.  生成项目。

     Visual Studio 创建压缩的文件，其中包含你的模板。 未部署，并且不可用的实验实例中。

## <a name="deployment"></a>部署

### <a name="to-deploy-the-project-or-item-template"></a>若要部署项目或项模板

1.  创建 VSIX 项目。 有关详细信息，请参阅[VSIX 项目模板](../extensibility/vsix-project-template.md)。

2.  将 VSIX 项目设置为启动项目。 在中**解决方案资源管理器**，选择 VSIX 项目节点，右键单击，并选择**设为启动项目**。

3.  项目模板项目设置为该 VSIX 项目的资产。 打开 *.vsixmanifest*文件。 转到**资产**选项卡，单击**新建**。

    1.  设置**类型**字段**Microsoft.VisualStudio.ProjectTemplate**或**Microsoft.VisualStudio.ItemTemplate**。

    2.  对于源，选择**当前解决方案中的项目**选项，并选择包含您的模板的项目。

4.  生成解决方案，然后按**F5**。 将显示在实验实例。

5.  对于项目模板项目，你应看到中列出的项目模板**新的项目**对话框 (**文件** > **新建** >  **项目**)、 Visual C# 或 Visual Basic 节点中。 对于项模板项目，你应看到中列出的项模板**添加新项**对话框。 若要查看**添加新项**对话框中，从**解决方案资源管理器**，选择项目节点，然后单击**添加** > **新项**).

## <a name="see-also"></a>请参阅

[Visual Studio 模板参考](../ide/creating-project-and-item-templates.md)
[Visual Studio 模板中的 NuGet 包](/nuget/visual-studio-extensibility/visual-studio-templates)