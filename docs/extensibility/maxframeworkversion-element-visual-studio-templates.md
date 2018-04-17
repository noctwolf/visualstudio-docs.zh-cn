---
title: MaxFrameworkVersion 元素 （Visual Studio 模板） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4bc28fcc35a4a59852ef6864886acff4dc87ef60
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>MaxFrameworkVersion 元素（Visual Studio 模板）

指定.NET Framework 所需的模板的最大版本。 它确定中可用的最大值**目标框架版本**下拉列表中的**新项目**对话框。 为了使用户能够选择的 framework 版本，还必须指定[RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md)作为模板的最低.NET Framework 版本。

> [!IMPORTANT]
> 从 Visual Studio 2017 版本 15.6，**目标框架版本**下拉列表中不再显示模板中的筛选器**模板**部分**新项目**对话框。 相反，**目标框架版本**下拉列表中为所选模板 framework 选取器函数。

 \<VSTemplate > \<TemplateData > \<MaxFrameworkVersion >

## <a name="syntax"></a>语法

```xml
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必需的元素。<br /><br /> 将此模板分类并定义中的显示方式**新项目**或**添加新项**对话框。|

## <a name="text-value"></a>文本值
 需要一个文本值。

 此文本必须允许通过模板的.NET framework 的最高版本号。

## <a name="remarks"></a>备注

`MaxFrameworkVersion` 是可选元素。 `MaxFrameworkVersion`应省略元素，除非它是必需的以免无意中限制为模板的受支持.NET Framework 版本。 它还应当.NET Framework 不是适用于模板才能省略。

## <a name="example"></a>示例

下面的示例演示一种标准的元数据[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]类模板。

```xml
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class template.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <RequiredFrameworkVersion>3.0</RequiredFrameworkVersion>
        <MaxFrameworkVersion>4.7.1</MaxFrameworkVersion>
        <DefaultName>MyClass</DefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem>MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

在此示例中，通过该模板后，所需的.NET framework 的最大版本由`MaxFrameworkVersion`，是 4.7.1。 使用此模板创建的项目可以面向.NET Framework 版本最 4.7.1 多。

## <a name="see-also"></a>另请参阅

- [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)
- [创建项目和项模板](../ide/creating-project-and-item-templates.md)
