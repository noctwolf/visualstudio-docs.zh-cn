---
title: "PropertyGroup 元素 (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#PropertyGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <PropertyGroup> element [MSBuild]
- PropertyGroup element [MSBuild]
ms.assetid: ff1e6c68-b9a1-4263-a1ce-dc3b829a64d4
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e19722c1da702684200d848eb62d1dd46a900590
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup 元素 (MSBuild)
包含一组用户定义的 [Property](../msbuild/property-element-msbuild.md) 元素。 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 项目中使用的每个 `Property` 元素必须是 `PropertyGroup` 元素的子元素。  

 \<Project>  
 \<PropertyGroup>  

## <a name="syntax"></a>语法  

```  
<PropertyGroup Condition="'String A' == 'String B'">  
    <Property1>...</Property1>  
    <Property2>...</Property2>  
</PropertyGroup>  
```  

## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  

### <a name="attributes"></a>特性  

|特性|描述|  
|---------------|-----------------|  
|条件|可选特性。<br /><br /> 要计算的条件。 有关详细信息，请参阅[条件](../msbuild/msbuild-conditions.md)。|  

### <a name="child-elements"></a>子元素  

|元素|描述|  
|-------------|-----------------|  
|[Property](../msbuild/property-element-msbuild.md)|可选元素。<br /><br /> 用户定义的属性名称，其中包含属性值。 `PropertyGroup` 元素中可能有零个或零个以上的 *Property* 元素。|  

### <a name="parent-elements"></a>父元素  

|元素|描述|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 项目文件必需的根元素。|  

## <a name="example"></a>示例  
 以下代码示例演示如何基于条件设置属性。 在此示例中，如果 `CompileConfig` 属性的值为 `DEBUG`，则会设置 `PropertyGroup` 元素内部的 `Optimization`、`Obfuscate` 和 `OutputPath` 属性。  

```xml  
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >  
    <Optimization>false</Optimization>  
    <Obfuscate>false</Obfuscate>  
    <OutputPath>$(OutputPath)\debug</OutputPath>  
</PropertyGroup>  
```  

## <a name="see-also"></a>请参阅  
 [项目文件架构参考](../msbuild/msbuild-project-file-schema-reference.md)  
 [MSBuild 属性](../msbuild/msbuild-properties.md)
