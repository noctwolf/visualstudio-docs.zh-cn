---
title: 如何：显示和隐藏寄存器组 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.registergroups
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, displaying and hiding register groups
- register groups, displaying and hiding
ms.assetid: 6be5dfb4-4cfe-4daf-b538-60405640857d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be702dcd19506e6da8fb1e291aa5262dbf4399b2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018444"
---
# <a name="how-to-display-and-hide-register-groups-c-c-visual-basic-f"></a>如何：显示和隐藏寄存器组 (C#，c + +、 Visual Basic 中， F#)

只有在“选项”对话框中“调试”节点下的“常规”类别中启用了地址级调试后，“寄存器”窗口才可用。

为避免杂乱，“寄存器”窗口中的寄存器按组显示。 右击“寄存器”窗口时，会看到包含这些组的快捷菜单。根据需要，可以按照以下过程显示或隐藏它们。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[重置设置](../ide/environment-settings.md#reset-settings)。

## <a name="display-or-hide-register-groups"></a>显示或隐藏寄存器组

1.  右击“寄存器”窗口。

2.  在快捷菜单上，选择要显示或隐藏的寄存器组。

     正在调试的硬件不支持的寄存器组在快捷菜单中被禁用，因此不能被选择。

## <a name="see-also"></a>请参阅

- [如何：使用“寄存器”窗口](../debugger/how-to-use-the-registers-window.md)