---
title: BuildProjectOnload 元素 （Visual Studio 模板） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b07d3074-0fc9-45e1-baf5-da6bd4f3f1c0
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1c194f4236f04eea7d8d1a156c8ee308ff58a143
ms.sourcegitcommit: aea5cdb76fbc7eb31d1e5cc3c8d6adb0c743220f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "47588910"
---
# <a name="buildprojectonload-element-visual-studio-templates"></a>BuildProjectOnload 元素（Visual Studio 模板）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[BuildProjectOnload 元素 （Visual Studio 模板）](https://docs.microsoft.com/visualstudio/extensibility/buildprojectonload-element-visual-studio-templates)。  
  
生成新的项目如下创建并将其添加到解决方案。 不生成整个解决方案。  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<BuildProjectOnLoad>  
  
## <a name="syntax"></a>语法  
  
```vb  
<BuildProjectOnLoad> true/false </BuildOnLoad>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|TemplateData|将此模板分类并定义显示在这种方式**新的项目**并**添加新项**对话框。|  
  
## <a name="text-value"></a>文本值  
 需要一个文本值。  
  
 文本必须是`true`或`false`以指示是否从模板创建时生成新的项目。  
  
## <a name="remarks"></a>备注  
 `BuildProjectOnLoad` 是可选元素。 默认值为 `false`。  
  
## <a name="example"></a>示例  
 下面的示例说明了 Visual C# 模板的元数据。  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <BuildProjectOnLoad>true</BuildProjectOnLoad>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>请参阅  
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)

