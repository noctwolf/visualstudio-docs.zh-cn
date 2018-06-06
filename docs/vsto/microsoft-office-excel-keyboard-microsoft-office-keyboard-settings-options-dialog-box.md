---
title: Microsoft Office Excel 键盘，Microsoft Office 键盘设置选项对话框
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fc71c699dfea11b8654791efdd52e4c0751a9762
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692442"
---
# <a name="microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box"></a>Microsoft Office Excel 键盘，Microsoft Office 键盘设置选项对话框
  Microsoft Office Excel 和 Visual Studio 同时处理键盘快捷方式。 相同的快捷组合键可以代表不同的命令在 Excel 和 Visual Studio 中的内容。 在 Visual Studio 中的文档级项目中打开 Excel 时，一次只有一个应用程序接收的快捷键命令。 默认情况下，Visual Studio 接收所有快捷键命令，但你可以在该文档通过选择具有焦点时接收它们的 Excel**动态键盘方案**。  
  
 如果你使用未分配给当前正在处理键盘快捷方式应用程序中的命令的快捷键，则该快捷键将被传递到其他应用程序。  
  
 你选择的选项将用于 Excel 项目实际上保留，直至你更改它。 所选内容不会影响 Microsoft Office Word 项目;你必须进行任何更改 word 使用 Microsoft Office Word 键盘选项。  
  
## <a name="uielement-list"></a>UIElement 列表  
 **Visual Studio 键盘方案**  
 Visual Studio 接收所有快捷键命令，即使 Excel 具有焦点。 例如，如果按键函数**F5** Excel 有焦点，Visual Studio 将启动调试你的解决方案。  
  
 **动态键盘方案**  
 仅当它具有焦点时，visual Studio 将接收的快捷键命令。 当 Excel 具有焦点时，Excel 会收到所有的快捷键命令。 例如，如果按键函数**F5** Excel 有焦点，Excel 将打开**转到**对话框。 如果按**F5**时 Visual Studio 具有焦点时，Visual Studio 将启动调试你的解决方案。  
  
## <a name="see-also"></a>请参阅  
 [Microsoft Office Word 键盘，Microsoft Office 键盘设置选项对话框](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)  
  
  