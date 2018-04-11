---
title: FormatUrl 任务 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8b353984812b8ce586054771355f023d433312b3
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
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
  
## <a name="see-also"></a>另请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)