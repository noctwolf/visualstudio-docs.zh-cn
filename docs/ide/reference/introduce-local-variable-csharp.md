---
title: "引入本地变量 - 代码生成 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 6ba9478c09e55df54f94ed93c7a694f798ae76b4
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="introduce-a-local-variable-in-c"></a>引入本地变量 (C#) #

功能：立即生成本地变量以替换现有表达式。

时机：如果有代码在本地变量中，稍后可轻松地重复使用它们时。

原因：可多次复制并粘贴代码以便在各自位置中使用它，但是执行一次操作、将结果存储在本地变量然后始终使用本地变量效果会更好。

方法：

1. 突出显示想要分配给一个新本地变量的表达式。

   ![突出显示的代码](media/local-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“为（出现的所有）'表达式'引入本地”，其中“表达式”是已突出显示的代码。
   * **鼠标**
     * 右键单击并选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“为（出现的所有）'表达式'引入本地”，其中“表达式”是已突出显示的代码。
     * 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

   ![引入本地预览](media/local-preview-cs.png)

   > [!TIP]
   > 进行选择前，使用预览窗口底部的[**预览更改**](../../ide/preview-changes.md)链接查看将发生的所有更改。

1. 将通过从本地变量的用法推断出的类型自动创建变量。  为新的本地变量键入新名称。

   ![引入本地结果](media/local-result-cs.png)

   > [!NOTE]
   > 可以使用“...出现的所有...”菜单选项替换发现的每个选定表达式的实例，不只是你已专门突出显示的表达式。

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)
