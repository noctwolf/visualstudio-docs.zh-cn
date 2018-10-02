---
title: SupportsCodeSeparation 元素 （Visual Studio 模板） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SupportsCodeSeparation
helpviewer_keywords:
- SupportsCodeSeparation element [Visual Studio Templates]
- <SupportsCodeSeparation> element [Visual Studio Templates]
ms.assetid: 8112aac8-a269-40e5-b92b-9b9a6ff5a542
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 492b77cf0eaa7f656de0df5ee2724945be980364
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480045"
---
# <a name="supportscodeseparation-element-visual-studio-templates"></a>SupportsCodeSeparation 元素（Visual Studio 模板）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[SupportsCodeSeparation 元素 （Visual Studio 模板）](https://docs.microsoft.com/visualstudio/extensibility/supportscodeseparation-element-visual-studio-templates)。  
  
指定是否**将代码放在单独的文件**中启用复选框**添加新项**对话框。  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<SupportsCodeSeparation >  
  
## <a name="syntax"></a>语法  
  
```  
<SupportsCodeSeparation> true/false </SupportsCodeSeparation>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必需的元素。<br /><br /> 将此模板分类并定义中的显示方式**新的项目**或**新项**对话框。|  
  
## <a name="text-value"></a>文本值  
 需要一个文本值。  
  
 文本必须是`true`或`false`，以指示是否**将代码放在单独的文件**中启用复选框**添加新项**对话框。  
  
## <a name="remarks"></a>备注  
 `SupportsCodeSeparation` 是可选元素。 默认值为 `false`。  
  
 `SupportsCodeSeparation`元素功能仅适用于 Web 项目模板。  
  
 代码分离或代码隐藏页模型，可将标记保留在一个文件和另一个文件中的编程代码中。 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 和其他.NET 语言使用此模型。  
  
## <a name="example"></a>示例  
 下面的示例指定要显示**将代码放在单独的文件**选项。  
  
```  
<VSTemplate Version="3.0.0" Type="Project"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>  
    <TemplateData>  
        <Name>MyWebProjecStarterKit</Name>  
        <Description>A simple Web template</Description>  
        <Icon>icon.ico</Icon>  
        <ProjectType>Web</ProjectType>  
        <ProjectSubType>CSharp</ProjectSubType>  
        <DefaultName>WebSite</DefaultName>  
        <SupportsCodeSeparation>true</SupportsCodeSeparation>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="WebApplication.webproj">  
            <ProjectItem>icon.ico</ProjectItem>  
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>  
            <ProjectItem>Default.aspx.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)

