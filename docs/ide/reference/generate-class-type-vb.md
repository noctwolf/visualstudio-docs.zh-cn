---
title: "生成类或类型 - 代码生成 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: ebc361fe-d9b1-4c7a-ae28-5e71b5775460
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vsl.GenerateFromUsage
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 4a4ff45a59fb53964a365f31cc4d5f48a5b159dc
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-class-or-type-in-visual-basic"></a>在 Visual Basic 中生成类或类型
功能：立即生成类或类型的代码。 

时机：引入一个新类或类型，并想要自动以适当的方式声明它时。  

原因：可以在使用类或类型前对其进行声明，但此功能将自动生成类或类型。 

方法：

1. 将光标放在有红色波形曲线的行上，该曲线指示使用了尚不存在的类。

   ![突出显示的代码](media/class-highlight-vb.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择其中一个选项。
   * **鼠标**
     * 右键单击并选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择其中一个选项。
     * 将鼠标悬停在红色波形曲线上，然后单击出现的 ![灯泡](media/bulb-vb.png) 图标。
     * 单击 ![灯泡](media/bulb-vb.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

   ![生成类预览](media/class-preview-vb.png)

   选择 | 描述
   --- | ---
   在新文件中生成类“TypeName” | 在名为 TypeName.cs/.vb 的文件中创建名为 TypeName 的类
   生成类“TypeName” | 在当前文件中创建名为 TypeName 的类。
   生成嵌套类“TypeName” | 在当前类中创建名为“TypeName”的嵌套类。
   生成新类型... | 使用所指定的所有属性创建新类或结构。

   >[!TIP]
   >进行选择前，使用预览窗口底部的[**预览更改**](../../ide/preview-changes.md)链接查看将发生的所有更改。

1. 如果选择“生成新类型...”项，将弹出对话框，以允许你执行一些其他操作。

   ![生成类型](media/class-newtype-vb.png)

   选择 | 描述
   --- | ---
   Access | 将类型设置为具有“默认”、“内部”或“公共”访问权限。
   类型 | 这可被设置为“类”或“结构”。
   name | 无法对此进行更改，将使用已键入的名称。
   项目 | 如果在你的解决方案中有多个项目，可以选择想要设置类/结构所在的位置。
   文件名 | 可以创建一个新文件，或将该类型添加到现有文件。

1. 将使用从其用法中推断出的构造函数自动创建类/结构。

   ![生成类结果](media/class-result-vb.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)