---
title: 在 Visual Basic 中重构“将类型移到匹配的文件”操作
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 00fab87a8fed4d1dcd9b4899551d68eaab28d46a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>“将类型移到匹配的文件”重构

此重构适用于：

- C#

- Visual Basic

功能：移动选定的类型到具有相同名称的单独文件。

时机：在想要分开的相同文件中有多个类、结构和接口等时。

原因：将多个类型置于相同的文件会使查找这些类型变得困难。 通过将类型移动到具有相同名称的文件，代码变得更具可读性且更易于导航。

## <a name="how-to"></a>操作说明

1. 突出显示要移动的类型名称，或将文本光标置于其中：

   - C#：

    ![突出显示的代码 - C#](media/movetype-highlight-cs.png)

   - Visual Basic：

    ![突出显示的代码 - Visual Basic](media/movetype-highlight-vb.png)

1. 接下来，执行以下操作之一：

   - **键盘**
     - 按“Ctrl”+**。** 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“将类型移动到 TypeName.cs”，其中“TypeName”是已选定的类型名称。
   - **鼠标**
     - 右键单击代码，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“将类型移动到 TypeName.cs”，其中“TypeName”是已选定的类型名称。

   此类型随解决方案一并移动到具有此名称的新文件。

   - C#：

    ![内联结果 - C#](media/movetype-result-cs.png)

   - Visual Basic：

    ![内联结果 - Visual Basic](media/movetype-result-vb.png)

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)