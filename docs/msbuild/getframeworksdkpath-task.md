---
title: GetFrameworkSdkPath 任务 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a3ce43a9b2acae5589e4b746ce4bf2b2a47b0111
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37946828"
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath 任务
检索 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)] 的路径。  
  
## <a name="task-parameters"></a>任务参数  
 下表描述了 `GetFrameworkSdkPath` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`FrameworkSdkVersion20Path`|可选的 `String` 只读输出参数。<br /><br /> 如果存在，则返回 .NET SDK 2.0 版的路径。 否则返回 `String.Empty`。|  
|`FrameworkSdkVersion35Path`|可选的 `String` 只读输出参数。<br /><br /> 如果存在，则返回 .NET SDK 3.5 版的路径。 否则返回 `String.Empty`。|  
|`FrameworkSdkVersion40Path`|可选的 `String` 只读输出参数。<br /><br /> 如果存在，则返回 .NET SDK 4.0 版的路径。 否则返回 `String.Empty`。|  
|`Path`|可选 `String` 输出参数。<br /><br /> 如果存在任何版本，则包含最新 .NET SDK 的路径。 否则返回 `String.Empty`。|  
  
## <a name="remarks"></a>备注  
 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，后者自身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension 基类](../msbuild/taskextension-base-class.md)。  
  
## <a name="example"></a>示例  
 以下示例使用 `GetFrameworkSdkPath` 任务将指向 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 的路径存储在 `SdkPath` 属性中。  
  
```xml  
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