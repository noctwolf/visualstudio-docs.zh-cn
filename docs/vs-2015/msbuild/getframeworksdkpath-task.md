---
title: GetFrameworkSdkPath 任务 | Microsoft Docs
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
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkSdkPath task [MSBuild]
- MSBuild, GetFrameworkSdkPath task
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3e35cac8399ab97ae3825e35de5b249db7e23a7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468891"
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[GetFrameworkSdkPath 任务](https://docs.microsoft.com/visualstudio/msbuild/getframeworksdkpath-task)。  
  
  
检索 [!INCLUDE[winsdklong](../includes/winsdklong-md.md)] 的路径。  
  
## <a name="task-parameters"></a>任务参数  
 下表描述了 `GetFrameworkSdkPath` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`FrameworkSdkVersion20Path`|可选的 `String` 只读输出参数。<br /><br /> 如果存在，则返回 .NET SDK 2.0 版的路径。 否则返回 `String.Empty`。|  
|`FrameworkSdkVersion35Path`|可选的 `String` 只读输出参数。<br /><br /> 如果存在，则返回 .NET SDK 3.5 版的路径。 否则返回 `String.Empty`。|  
|`FrameworkSdkVersion40Path`|可选的 `String` 只读输出参数。<br /><br /> 如果存在，则返回 .NET SDK 4.0 版的路径。 否则返回 `String.Empty`。|  
|`Path`|可选 `String` 输出参数。<br /><br /> 如果存在任何版本，则包含最新 .NET SDK 的路径。 否则返回 `String.Empty`。|  
  
## <a name="remarks"></a>备注  
 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，后者自身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="example"></a>示例  
 以下示例使用 `GetFrameworkSdkPath` 任务将指向 [!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)] 的路径存储在 `SdkPath` 属性中。  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkSdkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="SdkPath" />  
        </GetFrameworkSdkPath>  
        <Message Text="$(SdkPath)"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)



