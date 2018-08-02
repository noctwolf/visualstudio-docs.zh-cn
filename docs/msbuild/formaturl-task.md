---
title: FormatUrl 任务 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FormatUrl task
- FormatUrl task [MSBuild]
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0c5e29260affb31d94d702fc19dad7704e3c110
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176169"
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
 除了具有表中列出的参数外，此任务还将从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension 基类](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)