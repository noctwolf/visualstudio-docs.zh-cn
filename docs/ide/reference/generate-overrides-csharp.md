---
title: "生成 Equals 和 GetHashCode 方法重写 - 代码生成 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 56b1753dbdcfbf8ce318e964a16879f02b1482c4
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-c"></a>生成 Equals 和 GetHashCode 方法重写 (C#) #

功能：让你生成 Equals 和 GetHashCode 方法。

时机：当具有表示应按某些字段进行比较（而非由内存中的对象位置进行比较）的“值”的类型时，将生成这些重写。

原因：如果实现值类型，应考虑重写 Equals 方法以获取提升的性能（优于 Equals 方法在 ValueType 上的默认实现）。

在实现引用类型时，如果你的类型可能是基类型（如点、字符串、BigNumber 等），则应考虑重写 Equals 方法。

重写 GetHashCode 方法以允许类型在哈希表中正常工作。 了解有关[相等运算符](/dotnet/standard/design-guidelines/equality-operators)的更多指南。

方法：

1. 将光标置于类型声明中。

   ![突出显示的代码](media/overrides-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成 Equals (对象)”或“生成 Equals 和 GetHashCode”。
   * **鼠标**
     * 右键单击并选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“生成 Equals（对象）”或“生成 Equals 和 GetHashCode”。
     * 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在包含类型声明的行上，它会出现在左边）。

   ![生成重写预览](media/overrides-preview-cs.png)

1. 选择想要生成重写方法的成员：

    ![生成重写对话框](media/overrides-dialog-cs.png)

    > [!TIP]
    > 也可以通过使用成员列表下方的复选框，从此对话框中生成运算符。

1. Equals 和 GetHashCode 重写将通过自动默认实现来生成。

   ![生成方法结果](media/overrides-result-cs.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)
