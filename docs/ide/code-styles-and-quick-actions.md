---
title: 代码样式首选项
ms.date: 03/12/2019
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: 689bdb62d5a4bc9aea21da67e8e5e844660756d6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62975288"
---
# <a name="code-style-preferences"></a>代码样式首选项

打开“工具”菜单中的“选项”对话框，即可设置 C# 和 Visual Basic 项目的代码样式首选项。 在“选项”对话框中，选择“文本编辑器”>“[C# 或 Basic]”>“代码样式” > “常规”。

列表中的每一项都会显示所选首选项的预览：

::: moniker range="vs-2017"

![代码样式选项](media/code-style-quick-actions-dialog.png)

::: moniker-end

::: moniker range=">=vs-2019"

![代码样式选项](media/vs-2019/code-style-quick-actions-dialog.png)

::: moniker-end

在此窗口中设置的选项适用于 Visual Studio 个性化帐户，并且不与特定项目或基本代码相关联。 此外，它们不会在生成时（包括在持续集成 (CI) 生成中）强制执行。 如果要将代码样式首选项与项目相关联，并在生成期间强制执行样式，请在 [.editorconfig 文件](#editorconfig-files) 中指定首选项。

> [!NOTE]
> 本主题适用于 Visual Studio  Windows 版。 对于 Visual Studio for Mac，请参阅 [Visual Studio for Mac 中的编辑器行为](/visualstudio/mac/editor-behavior)。

## <a name="editorconfig-files"></a>EditorConfig 文件

另外，还可以通过将 [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) 文件添加到项目来指定 .NET 的代码样式设置。

::: moniker range=">=vs-2019"

单击“通过设置生成 .editorconfig 文件”，基于在此“选项”页上设置的选项来自动生成编码样式 .editorconfig 文件。

![通过 VS 2019 中的设置生成 editorconfig 文件](media/vs-2019/generate-editorconfig-file-small.png)

::: moniker-end

EditorConfig 文件与基本代码（而不是 Visual Studio 个性化帐户）相关联。 EditorConfig 文件中的设置优先于“选项”对话框中选择的选项。 如果想要将所有参与者的编码样式强制执行到存储库或项目，请使用 EditorConfig 文件。

## <a name="preference-and-severity"></a>首选项和严重级别

对于此页上的每个样式设置，可使用每行相应的下拉列表设置“首选项”和“严重性”值。 严重性可设置为“无”、“建议”、“警告”或“错误”。 如果想要为某个代码样式启用[快速操作](../ide/quick-actions.md)，请确保“严重性”设置为“无”以外的其他项。 “快速操作”灯泡![灯泡](media/light-bulb-dropdown.png)、错误灯泡![错误灯泡](media/error-bulb.png)或螺丝刀![螺丝刀](media/screwdriver.png)图标将在使用了非首选样式时出现，你可选择“快速操作”列表上的选项将代码自动重写为首选样式。

## <a name="format-document-command"></a>“设置文档格式”命令

可配置“设置文档格式”命令（“编辑” > “高级” > “设置文档格式”），从而对文件执行其他代码清理，例如删除 Using 和对其排序，或者应用代码样式首选项。 可定义希望“设置文档格式”在[设置格式”选项页面](reference/options-text-editor-csharp-formatting.md#format-document-settings)上应用的设置。

代码清理按照 .editorconfig 文件中配置的设置进行操作。如果缺少该规则或文件，则按照通过“工具” > “选项” > “文本编辑器” > “C#”>[“代码样式”或“格式”]中设定的设置进行操作。

在 Visual Studio 中首次触发“设置文档格式”命令时，将显示一个黄色信息栏，提示你配置代码清理设置。

> [!TIP]
> 严重性配置为“无”的规则不参与代码清理，但可通过“快速操作和重构”菜单单独应用。

## <a name="see-also"></a>请参阅

- [快速操作](../ide/quick-actions.md)
- [EditorConfig 的 .NET 编码约定设置](../ide/editorconfig-code-style-settings-reference.md)
- [编辑器行为 (Visual Studio for Mac)](/visualstudio/mac/editor-behavior)