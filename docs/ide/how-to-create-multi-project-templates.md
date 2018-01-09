---
title: "如何：创建多项目模板 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, creating multi-project templates
- project templates, creating multi-project templates
- multi-project templates
ms.assetid: 8c7f7065-137e-40ad-868d-37e007270efd
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ac7701e3e4dc11bc5634436c3e6f831f6711e514
ms.sourcegitcommit: 03a74d29a1e0584ff4808ce6c9e812b51e774905
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2018
---
# <a name="how-to-create-multi-project-templates"></a>如何：创建多项目模板
多项目模板用作两个或多个项目的容器。 如果基于多项目模板的项目是从“新建项目”对话框中创建的，则模板中的每个项目都会添加到解决方案。  

 多项目模板是两个或多个项目模板，并随附一个 `ProjectGroup` 类型的根模板。

 多项目模板的行为也不同于常规模板。 多项目模板具有以下独特的特征：  
  
-   无法通过“新建项目”对话框向多项目模板中的各个项目分配名称。 改为使用 `ProjectTemplateLink` 元素的 `ProjectName` 属性指定每个项目的名称。 有关详细信息，请参阅下一节的第一个示例。  
  
-   多项目模板可以包含以不同的语言编写的项目，但通过使用 `ProjectType` 元素，仅可将整个模板本身放置在一个类别中。  
  
### <a name="to-create-a-multi-project-template"></a>创建多项目模板  
  
1.  创建要在多项目模板中包括的项目：
    1.  创建项目。  
  
    > [!NOTE]
    >  如果命名的项目将成为模板的源，则只使用有效的标识符字符。 从采用无效字符命名的项目中导出的模板会导致在将来基于模板的项目中产生编译错误。 有关有效的标识符字符的详细信息，请参阅[已声明的元素名称](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)。  
  
    2.  编辑项目，直到可以将它导出为一个模板。  
  
    3.  根据需要编辑代码文件，指出应替换参数的位置。 有关参数替换的详细信息，请参阅[如何：替换模板中的参数](../ide/how-to-substitute-parameters-in-a-template.md)。  
  
    4.  在“项目”菜单上，单击“导出模板”。 “导出模板”向导随即打开。  
  
    5.  单击“项目模板”。  
  
    6.  如果当前解决方案中具有多个项目，请选择要导出到模板中的项目。  
  
    7.  单击 **“下一步”**。  
  
    8.  选择模板的图标和预览图像。 这些将出现在“新建项目”对话框中。  
  
    9. 输入模板名称和说明。  
  
    10. 单击 **“完成”**。 项目会导出到一个 .zip 文件中，并放在指定的输出位置，还可以导入到 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]（如果选择）。  
  
2.  从生成的 zip 文件中，将 .vstemplate 文件提取到用来导出模板的项目文件所在的同一目录。

3.  创建根 .vstemplate 文件，使其包含多项目模板的元数据。 有关详细信息，请参阅下一节的第一个示例。  
  
4.  选择要在模板中包含的文件和文件夹，右键单击所选文件，单击“发送至”，然后单击“压缩的文件夹(zip 格式)”。 这些文件和文件夹会压缩到一个 .zip 文件中。  
  
> [注意!] 多项目模板必须包括以下各项，并压缩为 .zip 文件：  
>   
> -   整个多项目模板的根 .vstemplate 文件。 此根 .vstemplate 文件包含“新建项目”对话框中显示的元数据，并指定查找此模板中项目的 .vstemplate 文件的位置。 此文件必须位于 .zip 文件的根目录中。  
>   
> -   一个或多个文件夹，其中包含完整的项目模板所需的文件。 这包括项目的所有代码文件，以及项目的 .vstemplate 文件。  
>   
> 例如，具有两个项目的多项目模板 .zip 文件具有以下文件和目录：  
>   
>  MultiProjectTemplate.vstemplate  
>   
>  \Project1\Project1.vstemplate  
>   
>  \Project1\Project1.vbproj  
>   
>  \Project1\Class.vb  
>   
>  \Project2\Project2.vstemplate  
>   
>  \Project2\Project2.vbproj  
>   
>  \Project2\Class.vb  
>   
>  多项目模板的根 .vstemplate 文件不同于单项目模板，表现在以下方面：  
>   
> -   `VSTemplate` 元素的 `Type` 属性包含值：`ProjectGroup`。 例如：  
>   
>     ```  
>     <VSTemplate Version="2.0.0" Type="ProjectGroup"  
>         xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
>     ```  
>   
> -   `TemplateContent` 元素包含的 `ProjectCollection` 元素具有一个或多个用于定义指向所含项目中 .vstemplate 文件的路径的 `ProjectTemplateLink` 元素。 例如:  
>   
>     ```  
>     <TemplateContent>  
>         <ProjectCollection>  
>             <ProjectTemplateLink>  
>                 Project1\Project1.vstemplate  
>             </ProjectTemplateLink>  
>             <ProjectTemplateLink>  
>                 Project2\Project2.vstemplate  
>             </ProjectTemplateLink>  
>         </ProjectCollection>  
>     </TemplateContent>  
>     ```  
>   
  
5.  将该 .zip 模板文件放入 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 项目模板目录。 默认情况下，此目录为 \My Documents\Visual Studio Version\Templates\ProjectTemplates\\。  
  
## <a name="example"></a>示例  
 此示例演示一个基本的多项目根 .vstemplate 文件。 在此示例中，模板包含两个项目：`My Windows Application` 和 `My Class Library`。 `ProjectName` 元素的 `ProjectTemplateLink` 特性可为 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 设置要分配给此项目的名称。 如果不存在 `ProjectName` 特性，则会使用 .vstemplate 文件的名称作为项目名称。  
  
```  
<VSTemplate Version="2.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <ProjectTemplateLink ProjectName="My Windows Application">  
                WindowsApp\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink ProjectName="My Class Library">  
                ClassLib\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="example"></a>示例  
 此示例使用 `SolutionFolder` 元素，可以将项目划分为两个组，`Math Classes` 和 `Graphics Classes`。 该模板包含四个项目，其中两个位于每个解决方案文件夹中。  
  
```  
<VSTemplate Version="2.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <SolutionFolder Name="Math Classes">  
                <ProjectTemplateLink ProjectName="MathClassLib1">  
                    MathClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="MathClassLib2">  
                    MathClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
            <SolutionFolder Name="Graphics Classes">  
                <ProjectTemplateLink ProjectName="GraphicsClassLib1">  
                    GraphicsClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="GraphicsClassLib2">  
                    GraphicsClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>请参阅  
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [如何：创建项目模板](../ide/how-to-create-project-templates.md)   
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [SolutionFolder 元素（Visual Studio 模板）](../extensibility/solutionfolder-element-visual-studio-templates.md)   
 [ProjectTemplateLink 元素（Visual Studio 模板）](../extensibility/projecttemplatelink-element-visual-studio-templates.md)
