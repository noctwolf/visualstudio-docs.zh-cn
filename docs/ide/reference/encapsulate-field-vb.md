---
title: "将字段重构为属性 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.encapsulatefield
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 010a297745ed6028f7ee127fffc210097d6d26f5
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="encapsulate-a-field-in-visual-basic"></a>封装字段 (Visual Basic)

功能：将字段转换为属性，并将该字段的所有用法更新为使用新创建的属性。

时机：想要将字段移到属性中，并更新对此字段的所有引用时。  

原因：想要为其他类提供字段的访问权限，但不想要这些字段拥有直接访问权限。  例如，通过将字段包装在属性中，可编写代码来验证正在分配的值。

方法：

1. 突出显示要封装的字段的名称，或将文本光标置于其中：

   ![突出显示的代码](media/encapsulate-highlight-vb.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+R”，然后按“Ctrl+E”。  （请注意，键盘快捷方式可能因所选的配置文件而有所不同。）
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择任意一个“封装字段”项。
   * **鼠标**
     * 选择“编辑 > 重构> 封装字段”。
     * 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择任意一个“封装字段”项。

   选择 | 描述
   --------- | -----------
   封装字段 (并使用属性) | 使用属性封装字段，并将此字段的所有用法更新为使用所生成的属性
   封装字段 (但仍使用字段) | 使用属性封装字段，但将此字段的所有用法保留不变

   选择后，将立刻创建属性并更新对字段的引用。

   > [!TIP]
   > 提交前，使用弹出窗口中的“[预览更改](../../ide/preview-changes.md)”链接查看最后的结果。

   ![“封装属性”的结果](media/encapsulate-result-vb.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)