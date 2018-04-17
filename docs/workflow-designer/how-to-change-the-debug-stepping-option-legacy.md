---
title: 如何： 更改调试单步执行选项 （旧版） |Microsoft 文档
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aedb8e738dc2e6ca2b066dd9a2cd42e332bbd8be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>如何：更改调试单步执行选项（旧版）
本主题介绍如何更改调试单步执行选项[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]具有并发操作的旧的 Windows 工作流设计器中的应用程序。 在需要面向 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 或 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 时，请使用旧 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]。

 在调试具有并发执行，如的旧活动**ParallelActivity**或**ConditionedActivityGroup**，你可以使用两个选项之一逐句通过代码。

 按照这些步骤在旧工作流项目中更改调试单步执行选项。

## <a name="procedures"></a>过程

#### <a name="to-change-the-debug-stepping-option"></a>更改调试单步执行选项

1.  启动 Visual Studio。

2.  打开现有的旧工作流项目，或创建使用并发活动并且面向 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 或 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] 的新项目。

3.  上**工作流**在旧菜单[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]，指向**调试**，然后指向**单步执行选项**。

4.  选择**实例**或**分支**。

## <a name="see-also"></a>请参阅

- [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)
- [调试单步执行选项（旧版）](../workflow-designer/debug-stepping-options-legacy.md)