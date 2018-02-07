---
title: "生成方法 - 代码生成 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683790b4-b68b-42d7-8dc4-a68eca05aa01
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 08e46cb961ecd6511f79410a7424969f2db227ed
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="generate-a-method-in-visual-basic"></a>在 Visual Basic 中生成方法
功能：将方法快速添加到类。 

时机：想要引入新方法，并想要自动以适当的方式声明它时。  

原因：可以在使用该方法和参数之前对其进行声明，但此功能可自动生成声明。 

方法：

1. 将光标放在有红色波形曲线的行上，该曲线指示使用了尚不存在的方法。

   ![突出显示的代码](media/method-highlight-vb.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成方法”。
   * **鼠标**
     * 单击右键，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成方法”。
     * 将鼠标悬停在红色波形曲线上，然后单击出现的 ![灯泡](media/bulb-vb.png) 图标。
     * 单击 ![灯泡](media/bulb-vb.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

   ![生成方法预览](media/method-preview-vb.png)

   >[!TIP]
   >进行选择前，使用预览窗口底部的[**预览更改**](../../ide/preview-changes.md)链接查看将发生的所有更改。

1. 将使用从方法的用法推断出的任意参数自动创建方法。

   ![生成方法结果](media/method-result-vb.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)