---
title: Microsoft Office Excel 键盘，Microsoft Office 键盘设置选项对话框
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.ExcelOptions.KeyboardMappingScheme
- VS.ToolsOptionsPages.Microsoft_Office_Keyboard_Settings.Microsoft_Office_Excel_Keyboard
- VS.ToolsOptionsPages.Microsoft_Office_Tools.Microsoft_Office_Excel.Keyboard
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- keyboard shortcuts, Office development in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 63f3bfc9295501d5f9b8f0267037302cdbb04a76
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62970209"
---
# <a name="microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box"></a>Microsoft Office Excel 键盘，Microsoft Office 键盘设置选项对话框
  Microsoft Office Excel 和 Visual Studio 同时处理键盘快捷方式。 在 Excel 中，在 Visual Studio 中不同的命令可以代表相同快捷键组合。 在 Visual Studio 中的文档级项目中打开 Excel 时，一次只有一个应用程序接收的快捷键命令。 默认情况下，Visual Studio 接收所有快捷方式命令，但您可以使 Excel 文档通过选择具有焦点时接收它们**动态键盘方案**。

 如果使用未分配给当前正在处理键盘快捷方式的应用程序中的命令的快捷键，快捷键被传递到其他应用程序。

 您选择的选项将在日后失效的 Excel 项目之前将其更改。 所选内容不会影响 Microsoft Office Word 项目中;必须使用 Microsoft Office Word 键盘选项进行一词的任何更改。

## <a name="uielement-list"></a>UIElement 列表
 **Visual Studio 键盘方案**Visual Studio 接收所有快捷方式命令，即使 Excel 具有焦点。 例如，如果按功能键**F5** Excel 有焦点，Visual Studio 将启动调试你的解决方案。

 **动态键盘方案**Visual Studio 仅具有焦点时接收的快捷键命令。 当 Excel 具有焦点时，Excel 将接收所有的快捷键命令。 例如，如果按功能键**F5** Excel 有焦点，Excel 将打开**转到**对话框。 如果按下**F5**时 Visual Studio 具有焦点时，Visual Studio 将启动调试你的解决方案。

## <a name="see-also"></a>请参阅
- [Microsoft Office Word 键盘，Microsoft Office 键盘设置选项对话框](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)
