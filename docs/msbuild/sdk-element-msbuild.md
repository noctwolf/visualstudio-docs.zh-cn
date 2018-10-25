---
title: Sdk 元素 (MSBuild) | Microsoft 文档
ms.custom: ''
ms.date: 01/25/2018
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Project
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Sdk element [MSBuild]
- <Sdk> element [MSBuild]
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1069a22e700eebfd9d1e8c387af99cf4241ffbe0
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49834170"
---
# <a name="sdk-element-msbuild"></a>Sdk 元素 (MSBuild)
引用 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 项目 SDK。  

 \<Project>  
 \<Sdk>  


## <a name="syntax"></a>语法  

```xml  
<Sdk Name="My.Custom.Sdk"
     Version="1.0.0" />  
```  

## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  

### <a name="attributes"></a>特性  

|特性|描述|  
|---------------|-----------------|  
|`Name`|必需的特性。<br /><br /> 项目 SDK 的名称。|  
|`Version`|可选特性。<br /><br /> 项目 SDK 的版本|  

### <a name="child-elements"></a>子元素  
 无。

### <a name="parent-elements"></a>父元素  

| 元素 | 描述 |
| - | - |
| [Project](../msbuild/project-element-msbuild.md) | [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 项目文件必需的根元素。 |

## <a name="see-also"></a>请参阅  
 [如何：引用 MSBuild 项目 SDK](../msbuild/how-to-use-project-sdk.md)   
 [项目文件架构参考](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)
