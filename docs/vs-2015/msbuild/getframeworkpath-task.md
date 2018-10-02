---
title: GetFrameworkPath 任务 | Microsoft Docs
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
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkPath task [MSBuild]
- MSBuild, GetFrameworkPath task
ms.assetid: 5b7bcdd7-d4a0-442d-af29-8aadb3b10598
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 792c6fd47882e0ff116859c80e3e406e875bf5fe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468666"
---
# <a name="getframeworkpath-task"></a>GetFrameworkPath 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[GetFrameworkPath 任务](https://docs.microsoft.com/visualstudio/msbuild/getframeworkpath-task)。  
  
  
检索 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 程序集的路径。  
  
## <a name="task-parameters"></a>任务参数  
 下表描述了 `GetFrameworkPath` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`FrameworkVersion11Path`|可选 `String` 输出参数。<br /><br /> 包含 framework 1.1 版程序集的路径（如存在）。 否则返回 `null`。|  
|`FrameworkVersion20Path`|可选 `String` 输出参数。<br /><br /> 包含 framework 2.0 版程序集的路径（如存在）。 否则返回 `null`。|  
|`FrameworkVersion30Path`|可选 `String` 输出参数。<br /><br /> 包含 framework 3.0 版程序集的路径（如存在）。 否则返回 `null`。|  
|`FrameworkVersion35Path`|可选 `String` 输出参数。<br /><br /> 包含 framework 3.5 版程序集的路径（如存在）。 否则返回 `null`。|  
|`FrameworkVersion40Path`|可选 `String` 输出参数。<br /><br /> 包含 framework 4.0 版程序集的路径（如存在）。 否则返回 `null`。|  
|`Path`|可选 `String` 输出参数。<br /><br /> 包含最新 framework 程序集的路径（如存在）。 否则返回 `null`。|  
  
## <a name="remarks"></a>备注  
 如果安装了多个版本的 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]，则此任务会返回运行 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 所需的版本。  
  
 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，后者自身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="example"></a>示例  
 以下示例使用 `GetFrameworkPath` 任务将指向 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 的路径存储在 `FrameworkPath` 属性中。  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="FrameworkPath" />  
        </GetFrameworkPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)



