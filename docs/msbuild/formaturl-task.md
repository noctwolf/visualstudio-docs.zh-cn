---
title: "FormatUrl 任务 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FormatUrl task
- FormatUrl task [MSBuild]
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3aa488a24646d9d3d3315efe5efca7dca53f68d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="formaturl-task"></a>FormatUrl 任务
将 URL 转换为正确的 URL 格式。  
  
## <a name="parameters"></a>参数  
 下表描述了 `FormatUrl` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`InputUrl`|可选 `String` 参数。<br /><br /> 指定要格式化的 URL。|  
|`OutputUrl`|可选 `String` 输出参数。<br /><br /> 指定已格式化的 URL。|  
  
## <a name="remarks"></a>备注  
 除具有表中列出的参数外，此任务还从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)