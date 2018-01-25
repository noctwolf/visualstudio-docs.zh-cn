---
title: "生成重写 - 代码生成 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 334f5a79dad1b7d2c14768d0698797a34ad039c5
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="generate-an-override-in-visual-basic"></a>生成重写 (Visual Basic)
功能：快速生成针对任意方法的代码，以从基类替代它。 

时机：想要重写一个基类方法并自动生成签名时。  

原因：可以自己编写方法签名，但此功能可自动生成签名。 

方法：

1. 在想要插入重写方法签名的地方键入 Overrides 关键字，后跟一个空格，IntelliSense 下拉列表将显示出来。

   ![重写 IntelliSense](media/override-intellisense-vb.png)

1. 通过使用鼠标单击要从基类重写的方法，或使用键盘导航到此方法并按 Enter，来选择相应的方法。

<!--
   >[!TIP]
   >* Use the Property icon ![Property icon](media/override-property-vb.png) to show or hide  Properties in the list.
   >* Use the Method icon ![Property icon](media/override-method-vb.png) to show or hide Methods in the list.
-->

1. 所选择的方法或属性将作为替代添加到类，以供实现。

   ![重写结果](media/override-result-vb.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md) 