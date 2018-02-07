---
title: "生成字段、属性或本地内容 - 代码生成 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 766311f0ba165c87e61bb873baa3ab2f0b2d1402
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="generate-a-field-property-or-local-in-visual-basic"></a>生成字段、属性或本地内容 (Visual Basic)
功能：为之前未声明的字段、属性或本地内容快速生成代码。 

时机：键入时想要引入新字段、属性或本地内容，并想要自动以适当的方式对其进行声明时。  

原因：可以在使用该字段、属性或本地内容之前对其进行声明，但此功能可自动生成声明和类型。 

方法：

1. 将光标放在有红色波形曲线的行上，该曲线指示使用了尚不存在的字段、本地内容或属性。

   ![突出显示的代码](media/field-highlight-vb.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成变量 ‘名称’ > 生成字段/属性/本地内容”。
   * **鼠标**
     * 单击右键，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成变量 ‘名称’ > 生成字段/属性/本地内容”。
     * 将鼠标悬停在红色波形曲线上，然后单击出现的 ![灯泡](media/bulb-vb.png) 图标。
     * 单击 ![灯泡](media/bulb-vb.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

   ![生成字段/属性/本地内容预览](media/field-preview-vb.png)

   >[!TIP]
   >进行选择前，使用预览窗口底部的[**预览更改**](../../ide/preview-changes.md)链接查看将发生的所有更改。

1. 将使用从字段/属性/本地内容的用法推断出的类型自动创建字段/属性/本地内容。

   ![生成字段/属性/本地内容结果](media/field-result-vb.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)