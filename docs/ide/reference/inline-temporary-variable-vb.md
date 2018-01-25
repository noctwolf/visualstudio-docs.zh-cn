---
title: "将临时变量替换为其值 (Visual Basic) | Microsoft 文档"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7553a67892322a1acb2db33d7a16b399b6f0b23a
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="inline-a-temporary-variable-in-visual-basic"></a>内联临时变量 (Visual Basic)

功能：删除临时变量并将其替换为其值。

时机：使用临时变量会使代码难以理解时。

原因：删除临时变量可使代码更易于理解。

方法：

1. 突出显示要内联的临时变量，或将文本光标置于其中：

   ![突出显示的代码](media/inline-highlight-vb.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单。
   * **鼠标**
     * 右键单击代码，选择“快速操作和重构”菜单。

1. 从“预览”弹出窗口选择“内联临时变量”。

   此变量将被删除且对此变量的使用将立即被其值所替代。

   ![内联结果](media/inline-result-vb.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)