---
title: Sdk 元素 (MSBuild) | Microsoft 文档
ms.date: 01/25/2018
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 24392fe34069025209f0e2c02e1231d1cbbe3397
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54993269"
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

|特性|说明|  
|---------------|-----------------|  
|`Name`|必需的特性。<br /><br /> 项目 SDK 的名称。|  
|`Version`|可选特性。<br /><br /> 项目 SDK 的版本|  

### <a name="child-elements"></a>子元素  
 无。

### <a name="parent-elements"></a>父元素  

| 元素 | 说明 |
| - | - |
| [Project](../msbuild/project-element-msbuild.md) | [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 项目文件必需的根元素。 |

## <a name="see-also"></a>请参阅  
 [如何：引用 MSBuild 项目 SDK](../msbuild/how-to-use-project-sdk.md)   
 [项目文件架构参考](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)
