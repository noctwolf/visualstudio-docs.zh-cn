---
title: "Visual Studio 代码样式首选项 | Microsoft Docs"
ms.custom: 
ms.date: 03/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.openlocfilehash: 24470f4fdb1a75d6ebd2743b2ade72e6195842b4
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2017
---
# <a name="code-style-preferences"></a>代码样式首选项

打开“工具”菜单中的“选项”对话框，即可设置 C# 和 Visual Basic 项目的代码样式首选项。 选择“文本编辑器”、“C#”或“Basic”、“代码样式”、“常规”。 此窗口中设置的选项适用于本地计算机。 列表中的每一项都会显示所选首选项的预览，如下所示。

![代码样式选项](media/code-style-quick-actions-dialog.png)

对于每个项，可使用每行相应的下拉列表设置“首选项”和“严重性”。 可将严重性设置为“无”、“建议”、“警告”或“错误”，Visual Studio 会作出相应反应。 如果要对这些代码样式使用[快速操作](quick-actions.md)以自动将代码重写为首选样式，请务必将其设置为除“无”以外的其他选项，以便在使用非首选样式时显示灯泡图标 ![小灯泡图标](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall")。 然后，通过单击灯泡图标或按“Ctrl+.”即可应用这些首选项， 前提是光标位于相应的代码行上。

也可以通过 [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) 文件管理 .NET 的代码样式设置。 在这种情况下，EditorConfig 文件中的设置优先于“选项”对话框所选选项。 可使用 EditorConfig 文件为整个存储库或项目强制执行和配置代码样式。

## <a name="see-also"></a>请参阅

[快速操作](quick-actions.md)  
[EditorConfig 的 .NET 编码约定设置](../ide/editorconfig-code-style-settings-reference.md)