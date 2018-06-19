---
title: 工作流设计器-如何： 更改调试单步执行选项 （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
ms.openlocfilehash: 31047cedd4e8772b9ebab4ef238a8fe32bc07663
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31971978"
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>如何：更改调试单步执行选项（旧版）

本主题介绍如何更改调试单步执行具有并发操作的旧的 Windows 工作流设计器中的 Windows Workflow Foundation (WF) 应用程序的选项。 当你需要以面向.NET Framework 版本 3.5 或 WinFX 时，请使用旧工作流设计器。

在调试具有并发执行，如的旧活动**ParallelActivity**或**ConditionedActivityGroup**，你可以使用两个选项之一逐句通过代码。

按照这些步骤在旧工作流项目中更改调试单步执行选项。

## <a name="procedures"></a>过程

### <a name="to-change-the-debug-stepping-option"></a>更改调试单步执行选项

1.  启动 Visual Studio。

2.  打开现有的旧工作流项目或创建使用并发活动和该目标的新项目，.NET Framework 版本 3.5 或 WinFX。

3.  上**工作流**菜单在旧工作流设计器中，依次指向**调试**，然后指向**单步执行选项**。

4.  选择**实例**或**分支**。

## <a name="see-also"></a>请参阅

- [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)
- [调试单步执行选项（旧版）](../workflow-designer/debug-stepping-options-legacy.md)