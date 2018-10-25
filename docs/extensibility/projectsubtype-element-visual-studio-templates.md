---
title: ProjectSubType 元素 （Visual Studio 模板） |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectSubType
helpviewer_keywords:
- ProjectSubType element [Visual Studio Templates]
- <ProjectSubType> element [Visual Studio Templates]
ms.assetid: f6895cd4-3e95-4f0e-aa9e-8c7750f46ed4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d1ca080ea61fbaaba7992fd8f4f1f4fbeac843d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49824320"
---
# <a name="projectsubtype-element-visual-studio-templates"></a>ProjectSubType 元素 （Visual Studio 模板）
将模板中指定的值的子类别归入`ProjectType`元素。  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<ProjectSubType >  
  
## <a name="syntax"></a>语法  
  
```xml  
<ProjectSubType> SubType </ProjectSubType>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下各部分描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必需的元素。<br /><br /> 将此模板分类并定义此模板在 **“新建项目”** 或 **“添加新项”** 对话框中的显示方式。|  
  
## <a name="text-value"></a>文本值  
 需要一个文本值。  
  
 此值指定模板的子类别。  
  
## <a name="remarks"></a>备注  
 `ProjectSubType` 是 `TemplateData` 的可选子元素。  
  
 `ProjectSubType`元素提供了到子类别[ProjectType](../extensibility/projecttype-element-visual-studio-templates.md)元素。 此值可以包括：  
  
- `SmartDevice-NETCFv1`： 指定此模板针对[!INCLUDE[Compact](../extensibility/includes/compact_md.md)]1.0 版。  
  
- `SmartDevice-NETCFv2`： 指定此模板针对[!INCLUDE[Compact](../extensibility/includes/compact_md.md)]2.0 版。  
  
  如果模板包含`ProjectType`具有值的元素`Web`，则`ProjectSubType`元素指定模板的编程语言。 此元素可以具有以下值：  
  
- `CSharp`： 指定此模板创建[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]Web 项目或项。  
  
- `VisualBasic`： 指定此模板创建[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]Web 项目或项。  
  
## <a name="example"></a>示例  
 下面的示例演示用于的项目模板的元数据[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]设备应用程序的目标[!INCLUDE[Compact](../extensibility/includes/compact_md.md)]2.0 版。  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic device template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProjectSubType>SmartDevice-NETCFv2</ProjectSubType>  
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
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)   
 [ProjectType 元素 （Visual Studio 模板）](../extensibility/projecttype-element-visual-studio-templates.md)