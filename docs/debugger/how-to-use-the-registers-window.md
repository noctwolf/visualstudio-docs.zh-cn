---
title: 在调试器中查看注册值 |Microsoft Docs
ms.custom: seodec18
ms.date: 11/19/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.registers
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- registers, debugging
- register contents
- flags, Registers window
- register groups
- debugging [Visual Studio], Registers window
- Registers window
ms.assetid: 2918ffa2-562f-40d6-9053-ef321bbeb767
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8622bb1288324429ad346834930559d1435ac6d5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867574"
---
# <a name="view-register-values-in-the-registers-window-c-c-visual-basic-f"></a>在寄存器窗口中查看注册值 (C#，c + +、 Visual Basic 中， F#)

**注册**Visual Studio 在调试期间，窗口显示寄存器内容。 有关寄存器背后概念的简要介绍并**注册**窗口中，请参阅[调试基础知识：“寄存器”窗口](../debugger/debugging-basics-registers-window.md).

> [!NOTE]
> 寄存器信息不可用的脚本或 SQL 应用。

在调试期间，注册值更改，因为应用程序中执行代码。 以红色中最近显示更改的值**注册**窗口。

为了减少混乱，“寄存器”窗口将寄存器组织成组，具体情况随平台和处理器类型的不同而不同。 您可以显示或隐藏寄存器组。 有关更多信息，请参见[如何：显示和隐藏寄存器组](../debugger/how-to-display-and-hide-register-groups.md)。

您可以编辑寄存器的值。 有关更多信息，请参见[如何：编辑寄存器值](../debugger/how-to-edit-a-register-value.md)。

**若要打开寄存器窗口**

1. 启用地址级调试，通过选择**启用地址级调试**中**工具**(或**调试**) >**选项** > **调试**。

1. 当调试正在运行或在断点处时，选择**调试** > **Windows** > **注册**，或按**Alt**+ **5**。

>[!NOTE]
>对话框和菜单命令可能会根据你的 Visual Studio 版本或设置不同。 若要更改设置，请选择**导入和导出设置**Visual studio**工具**菜单。 有关详细信息，请参阅[重置设置](../ide/environment-settings.md#reset-settings)。

### <a name="see-also"></a>请参阅

- [调试基础知识：“寄存器”窗口](../debugger/debugging-basics-registers-window.md)
- [查看调试器中的数据](../debugger/viewing-data-in-the-debugger.md)
