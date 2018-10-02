---
title: ResolveNonMSBuildProjectOutput 任务 | Microsoft Docs
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
- MSBuild, ResolveNonMSBuildProjectOutput task
- ResolveNonMSBuildProjectOutput task [MSBuild]
ms.assetid: a0b8fcec-8c8d-4867-85ac-5304c5108e5e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 48a67d895c08d5966c2ea4b40140382db9157763
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477215"
---
# <a name="resolvenonmsbuildprojectoutput-task"></a>ResolveNonMSBuildProjectOutput 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[ResolveNonMSBuildProjectOutput 任务](https://docs.microsoft.com/visualstudio/msbuild/resolvenonmsbuildprojectoutput-task)。  
  
  
确定非 MSBuild 项目引用的输出文件。  
  
## <a name="parameters"></a>参数  
 下表描述了 `ResolveNonMSBuildProjectOutput` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`PreresolvedProjectOutputs`|可选 `String` 参数。<br /><br /> 指定包含解析的项目输出的 XML 字符串。|  
|`ProjectReferences`|必选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 指定项目引用。|  
|`ResolvedOutputPaths`|可选的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 输出参数。<br /><br /> 包含已解析引用路径的列表（并保留原始项目引用特性）。|  
|`UnresolvedProjectReferences`|可选的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 输出参数。<br /><br /> 包含项目引用项的列表，其中这些项无法使用输出的预解析列表进行解析。<br /><br /> 因为 Visual Studio 只预解析非 MSBuild 项目，这意味着此列表中的项目引用都采用 MSBuild 格式。|  
  
## <a name="remarks"></a>备注  
 除了具有表中列出的参数外，此任务还将从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)



