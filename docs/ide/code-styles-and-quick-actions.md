---
title: 代码样式首选项
ms.date: 03/10/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: e1875099fa73fc994643b137807d1b0e1ed485c9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53949941"
---
# <a name="code-style-preferences"></a>代码样式首选项

打开“工具”菜单中的“选项”对话框，即可设置 C# 和 Visual Basic 项目的代码样式首选项。 在“选项”对话框中，选择“文本编辑器”>“[C# 或 Basic]”>“代码样式” > “常规”。 此窗口中设置的选项仅适用于本地计算机。

列表中的每一项都会显示所选首选项的预览：

![代码样式选项](media/code-style-quick-actions-dialog.png)

> [!NOTE]
> 本主题适用于 Windows 上的 Visual Studio。 对于 Visual Studio for Mac，请参阅 [Visual Studio for Mac 中的编辑器行为](/visualstudio/mac/editor-behavior)。

## <a name="preference-and-severity"></a>首选项和严重级别

对于每个项，可使用每行相应的下拉列表设置“首选项”和“严重性”值。 严重性可设置为“无”、“建议”、“警告”或“错误”。 如果想要为某个代码样式启用[快速操作](../ide/quick-actions.md)，请确保“严重性”设置为“无”以外的其他项。 “快速操作”灯泡图标![小灯泡图标](media/vs2015_lightbulbsmall.png)将在使用了非首选样式时出现，你可选择“快速操作”列表上的选项将代码自动重写为首选样式。

## <a name="editorconfig-files"></a>EditorConfig 文件

也可以通过 [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) 文件管理 .NET 的代码样式设置。 EditorConfig 文件中的设置优先于“选项”对话框所选选项。 可使用 EditorConfig 文件为整个存储库或项目强制执行和配置代码样式。

## <a name="format-document-command"></a>“设置文档格式”命令

在 Visual Studio 2017 版本 15.8 及更高版本中，可配置“设置文档格式”命令（“编辑” > “高级” > “设置文档格式”），从而对文件执行其他代码清理，例如删除 Using 和对其排序，或者应用代码样式首选项。 可定义希望“设置文档格式”在[设置格式”选项页面](reference/options-text-editor-csharp-formatting.md#format-document-settings)上应用的设置。

代码清理按照 .editorconfig 文件中配置的设置进行操作。如果缺少该规则或文件，则按照通过“工具” > “选项” > “文本编辑器” > “C#”>[“代码样式”或“格式”]中设定的设置进行操作。

在 Visual Studio 2017 中首次触发“设置文档格式”命令时，将显示一个黄色信息栏，提示你配置代码清理设置。

> [!TIP]
> .editorconfig 文件中配置为“无”的规则不参与代码清理，但可通过“快速操作和重构”菜单单独应用。

## <a name="see-also"></a>请参阅

- [快速操作](../ide/quick-actions.md)
- [EditorConfig 的 .NET 编码约定设置](../ide/editorconfig-code-style-settings-reference.md)
- [编辑器行为 (Visual Studio for Mac)](/visualstudio/mac/editor-behavior)