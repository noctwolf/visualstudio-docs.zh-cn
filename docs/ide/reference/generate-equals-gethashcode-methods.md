---
title: 在 Visual Studio 中生成 C# Equals 和 GetHashCode 方法重写
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 9af687eb4b39afdbe9fd34df1aa03f18ce243ef8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49903109"
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-visual-studio"></a>在 Visual Studio 中生成 C# Equals 和 GetHashCode 方法重写

此代码生成适用于：

- C#

功能：让你生成 Equals 和 GetHashCode 方法。

适用情况：当具备的类型应按一个或多个字段进行比较，而不是按内存中的对象位置进行比较时，生成这些重写。

操作原因：

- 如果实现值类型，则应考虑重写 Equals 方法，针对 Equals 方法在 ValueType 上的默认实现提升相关性能。

- 在实现引用类型时，如果类型看起来像基类型（如点、字符串和 BigNumber 等），请考虑重写 Equals 方法。

- 重写 GetHashCode 方法，使类型能在哈希表中正常工作。 了解有关[相等运算符](/dotnet/standard/design-guidelines/equality-operators)的更多指南。

## <a name="how-to"></a>操作说明

1. 将光标置于类型声明中。

   ![突出显示的代码](media/overrides-highlight-cs.png)

1. 接下来，执行以下操作之一：

   - **键盘**
      - 按“Ctrl”+**。** 触发“快速操作和重构”菜单。
   - **鼠标**
      - 右键单击并选择“快速操作和重构”菜单。
      - 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在包含类型声明的行上，它会出现在左边）。

   ![生成重写预览](media/overrides-preview-cs.png)

1. 从下拉菜单中选择“生成 Equals(object)”或“生成 Equals 和 GetHashCode”。

1. 在“选取成员”对话框中，选择要为其生成方法的成员：

    ![生成重写对话框](media/overrides-dialog-cs.png)

    > [!TIP]
    > 也可以通过使用成员列表下方的复选框，从此对话框中生成运算符。

   通过默认实现来生成 Equals 和 GetHashCode 重写。

   ![生成方法结果](media/overrides-result-cs.png)

## <a name="see-also"></a>请参阅

- [代码生成](../code-generation-in-visual-studio.md)
- [预览更改](../../ide/preview-changes.md)