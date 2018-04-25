---
title: XslTransformation 任务 | Microsoft Docs
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
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a6de215dd429b77d382f48da47554268ad1d488b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="xsltransformation-task"></a>XslTransformation 任务
通过使用 XSLT 或编译的 XSLT 转换 XML 输入并输出到输出设备或文件。  
  
## <a name="parameters"></a>参数  
 下表描述了 `XslTransformation` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`OutputPaths`|必选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 指定 XML 转换的输出文件。|  
|`Parameters`|可选 `String` 参数。<br /><br /> 指定 XSLT 输入文档的参数。|  
|`XmlContent`|可选 `String` 参数。<br /><br /> 指定 XML 输入为字符串。|  
|`XmlInputPaths`|可选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 指定 XML 输入文件。|  
|`XslCompiledDllPath`|可选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定已编译的 XSLT。|  
|`XslContent`|可选 `String` 参数。<br /><br /> 指定 XSLT 输入为字符串。|  
|`XslInputPath`|可选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定 XSLT 输入文件。|  
  
## <a name="remarks"></a>备注  
 除了具有表中列出的参数外，此任务还将从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)