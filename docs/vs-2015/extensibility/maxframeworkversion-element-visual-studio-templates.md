---
title: MaxFrameworkVersion 元素 （Visual Studio 模板） |Microsoft Docs
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
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 94b12af3d2b0c455ae321b3329b1f90d2ab35fb2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49276817"
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>MaxFrameworkVersion 元素（Visual Studio 模板）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

指定模板所需的.NET framework 的最大版本。 它确定是否在显示该模板**模板**一部分**添加新项目**对话框中，基于在选择的值**目标框架版本**的框**添加新项目**对话框。  
  
 \<VSTemplate >  
 \<MaxFrameworkVersion >  
  
## <a name="syntax"></a>语法  
  
```  
<MaxFrameworkVersion> ... </MaxFrameworkVersion>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必需的元素。<br /><br /> 此模板分类并定义如何显示在**新的项目**或**添加新项**对话框。|  
  
## <a name="text-value"></a>文本值  
 需要一个文本值。  
  
 此文本必须由模板允许的.NET framework 的最高版本号。  
  
## <a name="remarks"></a>备注  
 `MaxFrameworkVersion` 是可选元素。 中的元素`TemplateData`.vstemplate 文件的部分作用的筛选器作为**模板**一部分**添加新项目**对话框。 只有的.NET Framework 需求的模板不超过`MaxFrameworkVersion`将显示元素的值，基于在选择的值**目标框架版本**的框**添加新项目**对话框。 `MaxFrameworkVersion`应忽略元素，除非它是必需的以免因疏忽而致使较新版本的.NET Framework 中使用时显示的模板。  
  
## <a name="example"></a>示例  
 下面的示例演示一种标准的元数据[!INCLUDE[csprcs](../includes/csprcs-md.md)]类模板。  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class template.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <MaxFrameworkVersion>3.5</MaxFrameworkVersion>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 在此示例中，最高版本的.NET framework 的所需的模板，以表示`MaxFrameworkVersion`，为 3.5。 仅当选择 3.0 或 3.5 中的时，将显示上面的模板**目标框架版本**框中**添加新项目**对话框。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)

