---
title: "生成重写 - 代码生成 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 3801d8ce60cf87126f8894bf44c77056f996cde1
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="generate-an-override-in-c"></a>生成重写 (C#) #

功能：快速生成针对任意方法的代码，以从基类替代它。

时机：想要替代一个基类方法并自动生成签名时。

原因：可以自己编写方法签名，但此功能可自动生成签名。

方法：

1. 在想要插入重写方法签名的地方键入 override 关键字，后跟一个空格，IntelliSense 下拉列表将出现。

   ![重写 IntelliSense](media/override-intellisense-cs.png)

1. 通过使用鼠标单击要从基类重写的方法，或使用键盘导航到此方法并按 Enter，来选择相应的方法。

   >[!TIP]
   >* 使用“属性”图标 ![“属性”图标](media/override-property-cs.png) 显示或隐藏列表中的属性。
   >* 使用“方法”图标 ![“方法”图标](media/override-method-cs.png) 显示或隐藏列表中的方法。

1. 所选择的方法或属性将作为替代添加到类，以供实现。

   ![重写结果](media/override-result-cs.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)
