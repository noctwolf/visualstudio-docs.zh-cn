---
title: FormatVersion 任务 | Microsoft Docs
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
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 21154f63d6209683d2d6c2261d3a6ec8198ea252
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481537"
---
# <a name="formatversion-task"></a>FormatVersion 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[FormatVersion 任务](https://docs.microsoft.com/visualstudio/msbuild/formatversion-task)。  
  
  
将修订号追加到版本号。  
  
-   案例 #1：输入：Version=\<undefined>; Revision=\<don't care>; 输出：OutputVersion ="1.0.0.0"  
  
-   案例 #2：输入：Version="1.0.0.*"  Revision="5" 输出：OutputVersion="1.0.0.5"  
  
-   案例 #3：输入：Version="1.0.0.0" Revision=\<don't care>; 输出：OutputVersion ="1.0.0.0"  
  
## <a name="parameters"></a>参数  
 下表描述了 `FormatVersion` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`FormatType`|可选 `String` 参数。<br /><br /> 指定格式类型。<br /><br /> -“Version”= 版本。<br />-“Path”=将“.”替换为“_”；|  
|`OutputVersion`|可选 `String` 输出参数。<br /><br /> 指定包含修订号的输出版本。|  
|`Revision`|可选 `Int32` 参数。<br /><br /> 指定要追加到该版本的修订。|  
|`Version`|可选 `String` 参数。<br /><br /> 指定要进行格式化的版本号字符串。|  
  
## <a name="remarks"></a>备注  
 除了具有表中列出的参数外，此任务还将从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)



