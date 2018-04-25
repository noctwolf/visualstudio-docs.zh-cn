---
title: 在 Visual Studio 中引入局部变量 | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b7af958e923c6af7929b8e4a9309c210dbf8ced5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="introduce-a-local-variable-in-visual-studio"></a>在 Visual Studio 中引入局部变量

此代码生成适用于：

- C#

- Visual Basic

功能：立即生成本地变量以替换现有表达式。

时机：如果有代码在本地变量中，稍后可轻松地重复使用它们时。

原因：可多次复制并粘贴代码以便在各自位置中使用它，但是执行一次操作、将结果存储在本地变量然后始终使用本地变量效果会更好。

## <a name="how-to"></a>操作说明

1. 突出显示想要分配给一个新本地变量的表达式。

   - C#：

    ![突出显示的代码 C#](media/local-highlight-cs.png)

   - Visual Basic：

    ![突出显示的代码 VB](media/local-highlight-vb.png)

1. 接下来，执行以下操作之一：

   - **键盘**
     - 按“Ctrl”+**。** 触发“快速操作和重构”菜单。
   - **鼠标**
     - 右键单击并选择“快速操作和重构”菜单。
     - 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

   ![引入本地预览](media/local-preview-cs.png)

1. 从下拉菜单中选择“引入‘表达式’（的所有匹配项）的本地内容”。

   > [!TIP]
   > 进行选择前，使用预览窗口底部的“预览更改”链接[查看将发生的所有更改](../../ide/preview-changes.md)。

   通过从局部变量用法推断出的类型来创建它。 为新的局部变量赋予新名称。

   - C#：

      ![“实现接口”的结果 C#](media/local-result-cs.png)

   - Visual Basic：

      ![“实现接口”的结果 VB](media/local-result-vb.png)

   > [!NOTE]
   > 可使用“...出现的所有...”菜单选项替换每个选定表达式的实例，而不仅替换特地突出显示的表达式。

## <a name="see-also"></a>请参阅

- [代码生成](../code-generation-in-visual-studio.md)
- [预览更改](../../ide/preview-changes.md)
