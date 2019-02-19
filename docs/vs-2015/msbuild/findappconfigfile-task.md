---
title: FindAppConfigFile 任务 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- FindAppConfigFile task [MSBuild]
- MSBuild, FindAppConfigFile task
ms.assetid: e292de3e-7482-4426-83ce-d921061808bf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8bfc2cb26e01552cf056f08ac6b32ba851aff7b3
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "54800362"
---
# <a name="findappconfigfile-task"></a>FindAppConfigFile 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
在提供的列表中查找 app.config 文件（若有）。  
  
## <a name="parameters"></a>参数  
 下表描述了 `FindAppConfigFile` 任务的参数。  
  
|参数|说明​​|  
|---------------|-----------------|  
|`AppConfigFile`|可选的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 输出参数。<br /><br /> 指定在列表中发现的第一个匹配项（如有）。|  
|`PrimaryList`|必选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 指定要在其中进行搜索的主列表。|  
|`SecondaryList`|必选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 指定要在其中进行搜索的辅助列表。|  
|`TargetPath`|必选 `String` 参数。<br /><br /> 指定要添加为元数据的值。|  
  
## <a name="remarks"></a>备注  
 除了具有表中列出的参数外，此任务还将从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)
