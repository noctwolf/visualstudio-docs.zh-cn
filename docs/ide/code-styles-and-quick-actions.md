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
ms.workload: multiple
ms.openlocfilehash: 741df95afdd7c7e8b6f0ba2de75c1465cd35cc97
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="code-style-preferences"></a>代码样式首选项

打开“工具”菜单中的“选项”对话框，即可设置 C# 和 Visual Basic 项目的代码样式首选项。 选择“文本编辑器” > “C#”或“基本” > “代码样式” > “常规”。 此窗口中设置的选项适用于本地计算机。 列表中的每一项都会显示所选首选项的预览，如下所示。

![代码样式选项](media/code-style-quick-actions-dialog.png)

对于每个项，可使用每行相应的下拉列表设置“首选项”和“严重性”值。 严重性可设置为“无”、“建议”、“警告”或“错误”。 如果想要为某个代码样式启用[快速操作](../ide/quick-actions.md)，请确保“严重性”设置为“无”以外的其他项。 快速操作灯泡图标![小灯泡图标](media/vs2015_lightbulbsmall.png)将在使用了非首选样式时出现，可以选择“快速操作”列表上的选项来自动将代码重写为首选样式。

也可以通过 [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) 文件管理 .NET 的代码样式设置。 在这种情况下，EditorConfig 文件中的设置优先于“选项”对话框所选选项。 可使用 EditorConfig 文件为整个存储库或项目强制执行和配置代码样式。

## <a name="see-also"></a>请参阅

[快速操作](../ide/quick-actions.md)  
[EditorConfig 的 .NET 编码约定设置](../ide/editorconfig-code-style-settings-reference.md)