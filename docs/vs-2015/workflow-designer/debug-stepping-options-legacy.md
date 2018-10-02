---
title: 调试单步执行选项 （旧版） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- branch stepping
- stepping, options in workflow debugging
- debugging, stepping options
- debugging workflows, stepping options
- instance stepping
ms.assetid: 3e9e3041-68c7-4f16-9bd6-da5e5144744b
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: b87496e3aa7ea25e4b7cd8decf53cb425448dbf5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478758"
---
# <a name="debug-stepping-options-legacy"></a>调试单步执行选项（旧版）
本主题介绍如何调试具有旧 [!INCLUDE[wf](../includes/wf-md.md)] 中的并发活动的 [!INCLUDE[wfd1](../includes/wfd1-md.md)] 应用程序。 在需要面向 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 或 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 时，请使用旧 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]。  
  
 在调试具有并发执行，如的旧活动**ParallelActivity**或**ConditionedActivityGroup**，可以使用以下两个选项之一来单步执行代码.  
  
-   **分支单步执行。** 单步执行此模式使您可以单步执行和调试复合活动的特定分支，例如**ParallelActivity**或**ConditionalActivityGroup**活动。 如果使用此选项进行调试，则看不到由于工作流中并发执行其他活动而导致的控件变化。 调试器只逐句通过当前选定分支中的活动，而工作流中的其他活动可以并发执行。 例如，默认情况下，在最左边的分支**ParallelActivity**活动和第一个子活动的**ConditionedActivityGroup**活动用于单步执行。 如果用户要调试任何其他分支或子活动，则必须在分支或子活动上放置显式断点。 触发断点时，在该分支中继续单步执行。  
  
-   **实例单步执行。** 使用此单步执行模式可以在工作流中逐句通过和调试并发执行的活动。 使用此选项，可以看到在工作流中运行并发执行活动时控件发生的变化。  
  
 默认情况下会选择分支单步执行选项，用户在调试旧工作流时可以在这两个选项之间切换。  
  
 在调试旧状态机工作流时，应选择实例单步执行选项。  
  
## <a name="see-also"></a>请参阅  
 [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)   
 [如何：更改调试单步执行选项（旧版）](../workflow-designer/how-to-change-the-debug-stepping-option-legacy.md)