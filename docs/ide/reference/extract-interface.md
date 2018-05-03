---
title: 在 Visual Studio 中重构“提取接口”操作
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.extractinterface
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 6afc2acab36be88b4eb554d1900e6b314e395bd9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="extract-an-interface-refactoring"></a>“提取接口”重构

此重构适用于：

- C#

- Visual Basic

功能：使用来自类、结构或接口的现有成员创建接口。

时机：有多个类、结构或接口具有可以通用的方法或这些方法可由其他类、结构或接口使用时。

原因：接口是面向对象设计的出色构造。 假设有各类动物（狗、猫、鸟），这些动物都具有吃、喝、睡等一些共同方法。 使用 IAnimal 这样的接口，狗、猫和鸟即可拥有适用于这些方法的共同“签名”。

## <a name="how-to"></a>操作说明

1. 突出显示要对其执行操作的类名称或仅将文本光标置于类名称中。

   - C#：

    ![突出显示的代码 - C#](media/extractinterface-highlight-cs.png)

   - Visual Basic：

    ![突出显示的代码 - Visual Basic](media/extractinterface-highlight-vb.png)

1. 接下来，执行以下操作之一：

   - **键盘**
     - 按“Ctrl+R”，然后按“Ctrl+I”。 （请注意，键盘快捷方式可能因所选的配置文件而有所不同。）
     - 按“Ctrl”+**。** 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“提取接口”。
   - **鼠标**
     - 选择“编辑”>“重构”>“提取接口”。
     - 右键单击类名称，选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“提取接口”。

1. 在弹出的“提取接口”对话框中，输入需提供的信息：

   ![提取接口](media/extractinterface-dialog-cs.png)

   | 字段 | 描述 |
   | --- | --- |
   | “新接口名称” | 要创建的接口的名称。 此处将默认为 “IClassName”，其中“ClassName”是上面所选类的名称。 |
   | “新文件名” | 将生成的包含接口的文件的名称。 与接口名称一样，此处将默认为 “IClassName”，其中“ClassName”是上面所选类的名称。 |
   | “选择构成接口的公共成员” | 要提取到接口的项。 你可以选择你想要的数量。 |

1. 选择 **“确定”**。

   在指定名称的文件中创建接口。 此外，所选类还会实现此接口。

   - C#：

    ![生成的类 - C#](media/extractinterface-class-cs.png)
    ![生成的接口 - C#](media/extractinterface-interface-cs.png)

   - Visual Basic：

    ![生成的类 - Visual Basic](media/extractinterface-class-vb.png)
    ![生成的接口 - Visual Basic](media/extractinterface-interface-vb.png)

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)