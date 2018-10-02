---
title: ProjectExtensions 元素 (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ProjectExtensions
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ProjectExtensions> element [MSBuild]
- ProjectExtensions element [MSBuild]
ms.assetid: f95f312f-ff92-41eb-9469-ad99e236a307
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 156a35a953169c5b1ed8208c8d4f044f7b9fa36f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484096"
---
# <a name="projectextensions-element-msbuild"></a>ProjectExtensions 元素 (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[ProjectExtensions 元素 (MSBuild)](https://docs.microsoft.com/visualstudio/msbuild/projectextensions-element-msbuild)。  
  
  
允许 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 项目文件包含非 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 信息。 `ProjectExtensions` 元素中的所有内容都将被 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 忽略。  
  
 \<Project>  
 \<ProjectExtensions>  
  
## <a name="syntax"></a>语法  
  
```  
<ProjectExtensions>  
    Non-MSBuild information to include in file.  
</ProjectExtensions>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 项目文件必需的根元素。|  
  
## <a name="remarks"></a>备注  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 项目中可能只会用到一个 `ProjectExtensions` 元素。  
  
## <a name="example"></a>示例  
 以下示例显示了存储在 `ProjectExtensions` 元素中的集成开发环境的信息。  
  
```  
<ProjectExtensions>  
    <VSIDE>  
        <External>  
            <!--  
            Raw XML passed to the IDE by an external source  
            -->  
        </External>  
    </VSIDE>  
</ProjectExtensions>  
```  
  
## <a name="see-also"></a>请参阅  
 [项目文件架构参考](../msbuild/msbuild-project-file-schema-reference.md)  
 [MSBuild](msbuild.md)


