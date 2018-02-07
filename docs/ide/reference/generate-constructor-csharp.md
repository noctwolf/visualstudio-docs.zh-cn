---
title: "生成构造函数 - 代码生成 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: b6e73b3b012547e98934bbcd76d1ee2eb0f3324d
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="generate-a-constructor-in-c"></a>生成构造函数 (C#) #
功能：为类上的新构造函数快速生成代码。 

时机：想要引入新构造函数，并想要自动以适当的方式声明它，或要修改现有的构造函数时。 

原因：可以在使用该构造函数之前对其进行声明，但此功能可自动使用适当的参数生成它。 此外，修改现有的构造函数需要更新所有的调用站点，使用此功能自动更新时除外。

方法：有多种生成构造函数的方法：
- [生成构造函数并选择成员](#pick)
- [从所选字段生成构造函数](#selection)
- [从新用法生成构造函数](#usage)
- [向现有的构造函数添加参数](#addparameter)
- [从构造函数参数创建和初始化字段/属性](#create)

## <a id = "pick"></a> 生成构造函数并选择成员
1. 将光标置于类中的任何空行：

   ![光标置于空行](media/constructor1-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成构造函数...”。
   * **鼠标**
     * 单击右键，选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成构造函数..”。
     * 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在此类中的空行上，它会出现在左边）。

   ![生成构造函数预览](media/constructor1-preview-cs.png)

1. 将显示一个对话框，可在其中选择要用作构造函数参数的成员，并可将它们排序（使用向上和向下箭头）。 按“确认”提交更改。
  
   ![选择成员对话框](media/constructor1-dialog-cs.png)

   >[!TIP] 
   >可以选中“添加 null 检查”复选框，为构造函数参数自动生成 null 检查。

1. 将按照指定的顺序使用所选的参数创建构造函数。
   ![生成构造函数结果](media/constructor1-result-cs.png)

## <a id="selection"></a> 从所选字段生成构造函数
1. 突出显示生成的构造函数要包含的成员：![突出显示成员](media/constructor2-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成构造函数 'TypeName(...)'”。
   * **鼠标**
     * 单击右键，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成构造函数 'TypeName(...)'”。
     * 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在包含选定内容的行上，它会出现在左边）。

     ![生成构造函数预览](media/constructor2-preview-cs.png)

1. 将使用所选的参数创建构造函数。
     ![生成构造函数结果](media/constructor2-result-cs.png)

## <a id="usage"></a> 从新用法生成构造函数
1. 将光标放在有红色波形曲线的行上，该曲线指示使用了尚不存在的构造函数。

   ![突出显示的代码](media/constructor-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“在 ‘TypeName’ 中生成构造函数”。
   * **鼠标**
     * 单击右键，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“在 ‘TypeName’ 中生成构造函数”。
     * 将鼠标悬停在红色波形曲线上，然后单击出现的 ![灯泡](media/bulb-cs.png) 图标。
     * 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

   ![生成构造函数预览](media/constructor-preview-cs.png)

   >[!TIP]
   >进行选择前，使用预览窗口底部的[**预览更改**](../../ide/preview-changes.md)链接查看将发生的所有更改。

1. 将使用从构造函数的用法推断出的任意参数自动创建构造函数。

   ![生成构造函数结果](media/constructor-result-cs.png)

## <a id="addparameter"></a> 向现有的构造函数添加参数
1. 向现有的对象实例化添加参数。

1. 将光标放在有红色波形曲线的行上，该曲线指示使用了尚不存在的构造函数。
    
    ![生成构造函数突出显示](media/constructor4-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“向 'TypeName(...)' 添加参数”。
   * **鼠标**
     * 单击右键，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“向 'TypeName(...)' 添加参数”。
     * 将鼠标悬停在红色波形曲线上，然后单击出现的 ![灯泡](media/bulb-cs.png) 图标。
     * 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边）。

    ![生成构造函数预览](media/constructor4-preview-cs.png)

1. 将使用从参数的用法推断出的类型自动添加参数。
   
   ![生成构造函数结果](media/constructor4-result-cs.png)

## <a id="create"></a> 从构造函数参数创建和初始化字段/属性
1. 从现有构造函数添加参数：

   ![生成构造函数突出显示](media/constructor5-highlight-cs.png)

1. 将光标置于新添加的参数中。

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“创建和初始化属性 'YourProperty'”或“创建和初始化字段 'YourField'”。
   * **鼠标**
     * 单击右键，然后选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“创建和初始化属性 'YourProperty'”或“创建和初始化字段 'YourField'”。
     * 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在包含所添加的参数的行上，它会出现在左边）。

   ![生成构造函数预览](media/constructor5-preview-cs.png)

1. 将创建字段/属性，并自动为其命名，使其与类型相匹配。

   ![生成构造函数结果](media/constructor5-result-cs.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)