---
title: MSBuild .Targets 文件 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- .Targets files
- MSBuild, .Targets files
ms.assetid: f6d98eb4-d2fa-49b7-8e3c-bae1ca3cf596
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93207bb46b8294fe0b4fb3d93416e2fdabe61273
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484208"
---
# <a name="msbuild-targets-files"></a>MSBuild .Targets 文件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[MSBuild。目标文件](https://docs.microsoft.com/visualstudio/msbuild/msbuild-dot-targets-files)。  
  
  
[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 包括多个 .targets 文件，文件内容包含常见方案的项、属性、目标和任务。 这些文件将自动导入到大多数 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 项目文件中，以便简化维护，增强可读性。  
  
 项目通常会导入一个或多个 .targets 文件以定义它们的生成过程。 例如由 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 创建的 [!INCLUDE[csprcs](../includes/csprcs-md.md)] 项目将导入 Microsoft.CSharp.targets，它可导入 Microsoft.Common.targets。 [!INCLUDE[csprcs](../includes/csprcs-md.md)] 项目本身会定义特定于该项目的项和属性，但 [!INCLUDE[csprcs](../includes/csprcs-md.md)] 项目的标准生成规则是在导入的 .targets 文件中进行定义。  
  
 `$(MSBuildToolsPath)` 值指定这些公用 .targets 文件的路径。 如果 `ToolsVersion` 为 4.0，则文件位于以下位置：`WindowsInstallationPath\Microsoft.NET\Framework\v4.0.30319\`  
  
> [!NOTE]
>  若要了解如何创建自己的目标，请参阅[目标](../msbuild/msbuild-targets.md)。 若要了解如何使用 `Import` 元素将项目文件插入到另一个项目文件，请参阅 [Import 元素 (MSBuild)](../msbuild/import-element-msbuild.md) 和[如何：在多个项目文件中使用同一目标](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md)。  
  
## <a name="common-targets-files"></a>公用 .Targets 文件  
  
|.Targets 文件|描述|  
|-------------------|-----------------|  
|Microsoft.Common.targets|定义 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 和 [!INCLUDE[csprcs](../includes/csprcs-md.md)] 项目标准生成过程中的步骤。<br /><br /> 由 Microsoft.CSharp.targets 和 Microsoft.VisualBasic.targets 文件导入，其中包括以下语句：`<Import Project="Microsoft.Common.targets" />`|  
|Microsoft.CSharp.targets|定义 Visual C# 项目标准生成过程中的步骤。<br /><br /> 由 Visual C# 项目文件 (.csproj) 导入，其中包括以下语句：`<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`|  
|Microsoft.VisualBasic.targets|定义 Visual Basic 项目标准生成过程中的步骤。<br /><br /> 由 Visual Basic 项目文件 (.vbproj) 导入，其中包括以下语句：`<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`|  
  
## <a name="see-also"></a>请参阅  
 [Import 元素 (MSBuild)](../msbuild/import-element-msbuild.md)   
 [MSBuild 参考](../msbuild/msbuild-reference.md)  
 [MSBuild](msbuild.md)


