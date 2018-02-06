---
title: "重构方法签名 (C#) | Microsoft Docs"
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
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 44aaf3f4a570600b715d6d54f5fd80da84611b94
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="change-a-method-signature-in-c"></a>更改方法签名 (C#) #

功能：删除或更改方法的参数顺序。

时机：想要移动或删除当前用于多个位置的方法参数时。  

原因：可以手动删除和重新排列参数，然后找到对此方法的所有调用并逐一更改，但这样可能会引发错误。  此重构工具可自动执行此任务。

方法：

1. 突出显示要修改的方法的名称或其用法之一，或将文本光标置于其中：

   ![突出显示的代码](media/changesignature-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+R”，然后按“Ctrl+V”。  （请注意，键盘快捷方式可能因所选的配置文件而有所不同。）
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“更改签名”。
   * **鼠标**
     * 选择“编辑 > 重构 > 删除参数”。
     * 选择“编辑 > 重构 > 重新排列参数”。
     * 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“更改签名”。

1. 在弹出的“更改签名”对话框中，可以使用右侧的按钮更改方法签名：

   ![“更改签名”对话框](media/changesignature-dialog-cs.png)

   | Button | 描述
   | ------ | ---
   | 上移/下移 | 在列表中向上和向下移动所选的参数
   | **移除**  | 从列表删除所选的参数
   | 还原 | 将所选择的已删除参数还原到列表

   > [!TIP]
   > 提交前，使用“[预览引用更改](../../ide/preview-changes.md)”复选框查看最后的结果。

1. 完成后，按“确定”按钮进行更改。

   ![“更改签名”的结果](media/changesignature-result-cs.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)