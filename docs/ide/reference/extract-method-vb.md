---
title: "在 Visual Basic 中提取方法 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractmethod
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: f9e55a41f9a61626e8fce18cb11da6edc8a8bced
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="extract-a-method-in-visual-basic"></a>在 Visual Basic 中提取方法

功能：将代码片段转换为独立的方法。

时机：需要从其他方法调用某些方法中现有的代码片段时。  

原因：可以复制/粘贴该代码，但这样会导致重复。  更好的解决方案是将此片段重构为独立的且可供任何其他方法自行调用的方法。

方法：

1. 突出显示要提取的代码：

   ![突出显示的代码](media/extractmethod-highlight-vb.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+R”，然后按“Ctrl+M”。  （请注意，键盘快捷方式可能因所选的配置文件而有所不同。）
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“提取方法”。
   * **鼠标**
     * 选择“编辑 > 重构 > 提取方法”。
     * 右键单击代码，然后选择“重构 > 提取 > 提取方法”。
     * 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“提取方法”。

   将立即创建方法。  现在可以在此处为方法重命名，只需键入新的名称即可。

   > [!TIP]
   > 还可以将注释和其他字符串更新为使用该新名称，也可在保存前使用“重命名”框（在 IDE 的右上方）中的复选框[预览更改](../../ide/preview-changes.md)。

   ![重命名方法](media/extractmethod-rename-vb.png)

1. 对更改感到满意时，单击“应用”按钮或按 Enter，即可提交所做的更改。

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)