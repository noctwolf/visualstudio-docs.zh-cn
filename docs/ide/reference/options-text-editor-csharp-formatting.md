---
title: 选项、文本编辑器、C#、格式设置
ms.date: 02/09/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Spacing
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.NewLines
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Indentation
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Wrapping
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.General
helpviewer_keywords:
- formatting options [C#]
- Text editor Options dialog box, formatting
ms.assetid: 5a7bb668-1d0c-4ffe-9508-24592813162e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 534460d0ad6b7290190a88b3714c7f1eb0972723
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="options-text-editor-c-formatting"></a>选项、文本编辑器、C#、格式设置

使用“格式设置”选项页可在代码编辑器中设置格式设置代码的选项。 要访问此选项页，请选择“工具” > “选项”，然后选择“文本编辑器” > “C#” > “代码样式” > “格式设置”。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

## <a name="general-settings"></a>常规设置

常规设置会影响代码编辑器将格式设置选项应用于代码的方式。

## <a name="uielement-list"></a>UIElement 列表

|Label|描述|
|-----------|-----------------|
|键入时自动格式化|取消选择时，禁用“format statement on ;”和“format block  on }”选项。|
|输入 ; 时自动设置语句格式|如果选中此项，会根据为编辑器选择的格式设置选项在完成时对语句进行格式设置。|
|在 } 后自动格式化程序块|如果选中此项，完成代码块后，立即根据为编辑器选择的格式设置选项设置代码块的格式。|
|返回时自动格式化|如果选中此项，将在按 Enter 时设置文本的格式，使其与为编辑器选择的格式设置选项一致。|
|粘贴时自动设置格式|如果选中此项，设置粘贴到编辑器中的文本的格式，使其与为编辑器选择的格式设置选项一致。|

## <a name="preview-window"></a>预览窗口

“缩进”、“新行”、“间距”和“包装”选项窗格都会显示一个预览窗口。 预览窗口显示每个选项的效果。 若要使用预览窗口，请选择一个格式设置选项。 预览窗口显示选定选项的示例。 通过选择单选按钮或复选框更改设置时，会更新预览窗口，使其显示出新设置的效果。

## <a name="remarks"></a>备注

每种语言下，“选项卡”页面的缩进选项仅确定你在行末按 Enter 时代码编辑器将光标放置的位置。 自动设置代码的格式时应用“格式设置”下的缩进选项，例如在选中“粘贴时自动设置格式”的情况下将代码粘贴到文件中，以及在手动键入要设置格式的代码块时。

## <a name="see-also"></a>请参阅

- [“选项”对话框 ->“环境”->“常规”](../../ide/reference/general-environment-options-dialog-box.md)
