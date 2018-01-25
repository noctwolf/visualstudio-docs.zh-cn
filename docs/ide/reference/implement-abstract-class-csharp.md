---
title: "实现抽象类 - 代码生成 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cfed7f-f090-4369-8a85-2dcd4c7cf12b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: f089ffbe33d4a36e84d6d39abb3b3db3c4b2aeb7
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="implement-an-abstract-class-in-c"></a>实现抽象类 (C#) #
功能：快速生成实现抽象类所需的代码。 

时机：想要继承抽象类时。  

原因：可以手动逐一实现各个抽象类，但此功能可自动生成所有方法签名。 

方法：

1. 将光标放在有红色波形曲线的行上，该曲线指示已继承抽象类但尚未实现所有所需的成员。

   ![突出显示的代码](media/abstract-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“实现抽象类”。
   * **鼠标**
     * 右键单击，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“实现抽象类”。
     * 将鼠标悬停在红色波形曲线上，然后单击出现的 ![灯泡](media/bulb-cs.png) 图标。
     * 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

   ![实现类预览](media/abstract-preview-cs.png)

   >[!TIP]
   >进行选择前，使用预览窗口底部的[**预览更改**](../../ide/preview-changes.md)链接查看将发生的所有更改。
   >
   >此外，你可以使用预览窗口底部的“文档”、“项目”和“解决方案”链接跨继承此抽象类的多个类创建适当的方法签名。

1. 将自动创建抽象方法签名，以供实现。

   ![实现类结果](media/abstract-result-cs.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)
