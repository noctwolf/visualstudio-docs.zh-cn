---
title: VCMessage 任务 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.task.vcmessage
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- VCMessage task (MSBuild (Visual C++))
- MSBuild (Visual C++), VCMessage task
ms.assetid: 956675fd-05dc-40b4-856f-616145103498
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d667c53e00e7b92d133c260b5c3cc471a64f355b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477304"
---
# <a name="vcmessage-task"></a>VCMessage 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[VCMessage 任务](https://docs.microsoft.com/visualstudio/msbuild/vcmessage-task)。  
  
  
记录生成期间的警告消息和错误消息。  
  
## <a name="remarks"></a>备注  
 此任务可帮助实现 Visual C++ 的 MSBuild，不能由用户调用。 有关详细信息，请参阅<xref:Microsoft.Build.Utilities.TaskLoggingHelper>。  
  
## <a name="parameters"></a>参数  
 下表描述了 VCMessage 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|**参数**|可选 **String** 参数。<br /><br /> 要显示的消息列表（以分号分隔）。|  
|**代码**|必需的 **String** 参数。<br /><br /> 限定消息的错误号。|  
|**Type**|可选 **String** 参数。<br /><br /> 指定要发出的消息类型。 指定 `"Warning"` 发出一条警告消息，或指定 `"Error"` 发出一条错误消息。|  
  
## <a name="see-also"></a>请参阅  
 [任务参考](../msbuild/msbuild-task-reference.md)



