---
title: "将临时变量替换为其值 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 626224e8ed90196294f7b3ded245bb5272f70595
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="inline-a-temporary-variable-with-c"></a>使用 C# 内联临时变量 #

功能：删除临时变量并将其替换为其值。

时机：使用临时变量会使代码难以理解时。

原因：删除临时变量可使代码更易于理解。

方法：

1. 突出显示要内联的临时变量，或将文本光标置于其中：

   ![突出显示的代码](media/inline-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单。
   * **鼠标**
     * 右键单击代码，然后选择“快速操作和重构”菜单。

1. 从“预览”弹出窗口选择“内联临时变量”。

   此变量将被删除且对此变量的使用将立即被其值所替代。

   ![内联结果](media/inline-result-cs.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)