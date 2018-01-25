---
title: "在 Visual Basic 中提取接口 | Microsoft Docs"
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
f1_keywords: vs.csharp.refactoring.extractinterface
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 98a3a96357eb6e7391eb92bd0ac3a53dd00f09f5
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="extract-an-interface-in-visual-basic"></a>在 Visual Basic 中提取接口

功能：使用来自类、结构或接口的现有成员创建接口。

时机：有多个类、结构或接口具有可以通用的方法或这些方法可由其他类、结构或接口使用时。

原因：接口是面向对象设计的出色构造。  假设有各类动物（狗、猫、鸟），这些动物都具有吃、喝、睡等一些共同方法。  使用 IAnimal 这样的接口，狗、猫和鸟即可拥有适用于这些方法的共同“签名”。  

方法：

1. 突出显示要对其执行操作的类名称或仅将文本光标置于类名称中。

   ![突出显示的代码](media/extractinterface-highlight-vb.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+R”，然后按“Ctrl+I”。  （请注意，键盘快捷方式可能因所选的配置文件而有所不同。）
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“提取接口”。
   * **鼠标**
     * 选择“编辑”>“重构”>“提取接口”。
     * 右键单击类名称，选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“提取接口”。

1. 在弹出的“提取接口”对话框中，输入要求提供的信息：![提取接口](media/extractinterface-dialog-vb.png)
   | 字段 | 描述 |
   | --- | --- |
   | “新接口名称” | 要创建的接口的名称。 此处将默认为 “IClassName”，其中“ClassName”是上面所选类的名称。 |
   | “新文件名” | 将生成的包含接口的文件的名称。 与接口名称一样，此处将默认为 “IClassName”，其中“ClassName”是上面所选类的名称。 |
   | “选择构成接口的公共成员” | 要提取到接口的项。  你可以选择你想要的数量。 |

1. 单击 **“确定”**。

   将在指定名称的文件中立即创建接口。  此外，选定的类现在将实现此接口。

   ![生成的类](media/extractinterface-class-vb.png)
   ![生成的接口](media/extractinterface-interface-vb.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)