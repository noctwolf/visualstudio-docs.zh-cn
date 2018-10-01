---
title: 如何： 更改调试单步执行选项 （旧版） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1fbe4ef5feeff7201a5c8772c1e754402db9ffd5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478902"
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>如何：更改调试单步执行选项（旧版）
本主题介绍如何在旧 [!INCLUDE[wf](../includes/wf-md.md)] 中，针对具有并发操作的 [!INCLUDE[wfd1](../includes/wfd1-md.md)] 应用程序更改调试单步执行选项。 在需要面向 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 或 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 时，请使用旧 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]。  
  
 在调试具有并发执行，如的旧活动**ParallelActivity**或**ConditionedActivityGroup**，可以使用两个选项之一来逐句通过代码。  
  
 按照这些步骤在旧工作流项目中更改调试单步执行选项。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-change-the-debug-stepping-option"></a>更改调试单步执行选项  
  
1.  启动 Visual Studio。  
  
2.  打开现有的旧工作流项目，或创建使用并发活动并且面向 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 或 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] 的新项目。  
  
3.  上**工作流**在旧菜单[!INCLUDE[wfd2](../includes/wfd2-md.md)]，依次指向**调试**，然后指向**单步执行选项**。  
  
4.  选择任一**实例**或**分支**。  
  
## <a name="see-also"></a>请参阅  
 [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)   
 [调试单步执行选项（旧版）](../workflow-designer/debug-stepping-options-legacy.md)