---
title: GenerateTrustInfo 任务 | Microsoft Docs
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
- MSBuild, GenerateTrustInfo task
- GenerateTrustInfo task [MSBuild]
ms.assetid: 3ca60816-4bb0-4fef-ae43-ca0bfb63def3
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f755994c09e0634df814683b77d925f2293b6cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469866"
---
# <a name="generatetrustinfo-task"></a>GenerateTrustInfo 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[GenerateTrustInfo 任务](https://docs.microsoft.com/visualstudio/msbuild/generatetrustinfo-task)。  
  
  
从基本清单以及从 `TargetZone` 和 `ExcludedPermissions` 属性生成应用程序信任。  
  
## <a name="parameters"></a>参数  
 下表描述了 `GenerateTrustInfo` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`ApplicationDependencies`|可选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 指定依赖项程序集。|  
|`BaseManifest`|可选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定要从中生成应用程序信任的基本清单。|  
|`ExcludedPermissions`|可选 `String` 参数。<br /><br /> 指定一个或多个要从区域默认权限集中排除的权限标识值（这些值由分号分隔）。|  
|`TargetZone`|可选 `String` 参数。<br /><br /> 指定区域默认权限集，该权限集是从计算机策略中获取的。|  
|`TrustInfoFile`|必需的 <xref:Microsoft.Build.Framework.ITaskItem> 输出参数。<br /><br /> 指定包含应用程序安全信任信息的文件。|  
  
## <a name="remarks"></a>备注  
 除了具有表中列出的参数外，此任务还将从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)



