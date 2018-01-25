---
title: "生成构造函数 - 代码生成 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 891a33b74927d45434c4614dc4c5d7f1533ba4c0
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-constructor-in-visual-basic"></a>生成构造函数 (Visual Basic)
功能：为类上的新构造函数快速生成代码。 

时机：想要引入新构造函数，并想要自动以适当的方式声明它时。  

原因：可以在使用该构造函数之前对其进行声明，但此功能可自动使用适当的参数生成它。 

方法：

1. 将光标放在有红色波形曲线的行上，该曲线指示使用了尚不存在的构造函数。

   ![突出显示的代码](media/constructor-highlight-vb.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“在 ‘TypeName’ 中生成构造函数”。
   * **鼠标**
     * 单击右键，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“在 ‘TypeName’ 中生成构造函数”。
     * 将鼠标悬停在红色波形曲线上，然后单击出现的 ![灯泡](media/bulb-vb.png) 图标。
     * 单击 ![灯泡](media/bulb-vb.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

   ![生成构造函数预览](media/constructor-preview-vb.png)

   >[!TIP]
   >进行选择前，使用预览窗口底部的[**预览更改**](../../ide/preview-changes.md)链接查看将发生的所有更改。

1. 将使用从构造函数的用法推断出的任意参数自动创建构造函数。

   ![生成构造函数结果](media/constructor-result-vb.png)
 
## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)