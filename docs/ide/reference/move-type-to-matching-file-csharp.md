---
title: "将类型移到匹配的文件 - 重构 (C#) | Microsoft Docs"
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
ms.openlocfilehash: 4b7b9b1ba52bed5d2bdf042db0149d799c489a7d
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="move-a-type-to-a-matching-file-in-c"></a>将类型移到匹配的文件 (C#) #

功能：移动选定的类型到具有相同名称的单独文件。

时机：在想要分开的相同文件中有多个类、结构和接口等时。

原因：将多个类型置于相同的文件会使查找这些类型变得困难。  通过将类型移动到具有相同名称的文件，代码变得更具可读性且更易于导航。

方法：

1. 突出显示要移动的类型名称，或将文本光标置于其中：

   ![突出显示的代码](media/movetype-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“将类型移动到 TypeName.cs”，其中“TypeName”是已选定的类型名称。
   * **鼠标**
     * 右键单击代码，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“将类型移动到 TypeName.cs”，其中“TypeName”是已选定的类型名称。

   此类型将立即移动到解决方案内具有此名称的新文件。

   ![内联结果](media/movetype-result-cs.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)