---
title: XmlPoke 任务 | Microsoft Docs
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
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 05bef838c905b12ba76d22bec901ae4eb3382c5f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="xmlpoke-task"></a>XmlPoke 任务
将 XPath 查询指定的值设置为 XML 文件。  
  
## <a name="parameters"></a>参数  
 下表描述了 `XmlPoke` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`Namespaces`|可选 `String` 参数。<br /><br /> 指定 XPath 查询前缀的命名空间。|  
|`Query`|可选 `String` 参数。<br /><br /> 指定 XPath 查询。|  
|`Value`|必选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定输出文件。|  
|`XmlInputPath`|可选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定 XML 输入为文件路径。|  
  
## <a name="remarks"></a>备注  
 除了具有表中列出的参数外，此任务还将从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)