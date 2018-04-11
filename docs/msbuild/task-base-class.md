---
title: 任务基类 | Microsoft Docs
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
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
caps.latest.revision: 6
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c27077237b3fd173be0ba368d1b34e54939ea1e2
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
---
# <a name="task-base-class"></a>任务基类
许多任务最终都继承自 <xref:Microsoft.Build.Utilities.Task> 类。 此类向派生自该类的任务添加几个参数。 本文档中列出了这些参数。  
  
## <a name="parameters"></a>参数  
 下表介绍此基类的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|可选 <xref:Microsoft.Build.Framework.IBuildEngine> 参数。<br /><br /> 指定可供任务使用的生成引擎接口。 生成引擎会自动设置此参数，以允许任务回调到其中。|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|可选 <xref:Microsoft.Build.Framework.IBuildEngine2> 参数。<br /><br /> 指定可供任务使用的生成引擎接口。 生成引擎会自动设置此参数，以允许任务回调到其中。<br /><br /> 这是一个便捷属性，使从此类继承的任务作者不必将值从 `IBuildEngine` 强制转换为 `IBuildEngine2`。|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|可选 <xref:Microsoft.Build.Framework.IBuildEngine3> 参数。<br /><br /> 指定主机使用的生成引擎接口。|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|可选 <xref:Microsoft.Build.Framework.ITaskHost> 参数。<br /><br /> 指定主机对象实例（可以为 null）。 如果主机 IDE 具有与此特定任务关联的主机对象，则生成引擎会设置此属性。|  
|<xref:Microsoft.Build.Utilities.Task.Log%2A>|可选 <xref:Microsoft.Build.Utilities.TaskLoggingHelper> 只读参数。<br /><br /> 日志记录帮助程序对象。|  
  
## <a name="see-also"></a>另请参阅  
 [任务参考](../msbuild/msbuild-task-reference.md)   
 [任务](../msbuild/msbuild-tasks.md)