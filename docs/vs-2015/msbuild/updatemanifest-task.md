---
title: UpdateManifest 任务 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
- MSBuild, UpdateManifest task
- UpdateManifest task [MSBuild]
ms.assetid: 1291fd33-b89e-4e15-8fb1-69f9625cf2d2
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 43286352ddeb4e2fb3610c5f0b7b67190b526f81
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49245487"
---
# <a name="updatemanifest-task"></a>UpdateManifest 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
更新清单中所选的属性并重新签名。  
  
## <a name="parameters"></a>参数  
 下表描述了 `UpdateManifest` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`ApplicationManifest`|必选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定应用程序清单。|  
|`ApplicationPath`|必选 `String` 参数。<br /><br /> 指定应用程序清单的路径。|  
|`InputManifest`|必选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定要更新的清单。|  
|`OutputManifest`|可选 <xref:Microsoft.Build.Framework.ITaskItem> 输出参数。<br /><br /> 指定包含更新的属性的清单。|  
  
## <a name="remarks"></a>备注  
 除了具有表中列出的参数外，此任务还将从 <xref:Microsoft.Build.Utilities.Task> 类继承参数。 有关这些其他参数的列表及其说明，请参阅[任务基类](../msbuild/task-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)



