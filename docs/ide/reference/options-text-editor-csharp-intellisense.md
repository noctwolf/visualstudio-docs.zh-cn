---
title: 选项，文本编辑器，C#，IntelliSense
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Intellisense
helpviewer_keywords:
- underlines, wavy
- IntelliSense [C#], options
- IntelliSense [C#], wavy underlines
- wavy underlines
- Text Editor Options dialog box, IntelliSense
ms.assetid: 3466dedb-e5f4-424c-8dd8-e4941b2f4fc2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: d8f6928dd09b971e2c5924d34058a1a0d5e28394
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="options-text-editor-c-intellisense"></a>选项，文本编辑器，C#，IntelliSense

使用“IntelliSense”选项页可修改影响 IntelliSense for C# 行为的设置。 要访问此选项页，请选择“工具” > “选项”，然后选择“文本编辑器” > “C#” > “IntelliSense”。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

“IntelliSense”选项页面包含以下选项：

## <a name="completion-lists"></a>完成列表

- 键入字符后显示完成列表*

   选择此选项后，IntelliSense 在你开始键入时会自动显示完成列表。 即使未选中此选项，仍可通过“IntelliSense”菜单或通过按 Ctrl+空格使用 IntelliSense 完成功能。

- 删除字符后显示完成列表

- 突出显示完成列表项的匹配部分

- 显示完成项筛选器

- 显示名称建议

### <a name="snippets-behavior"></a>片段行为

- 从不包含片段

   选择此选项后，IntelliSense 绝不将 C# 代码片段的别名添加到完成列表中。

- 始终包含片段

   选择此选项后，IntelliSense 将 C# 代码片段的别名添加到完成列表中。 如果代码片段别名与关键字相同（例如均为 [class](/dotnet/csharp/language-reference/keywords/class)），则快捷方式将替代关键字。 有关详细信息，请参阅 [C# 代码片段](../../ide/visual-csharp-code-snippets.md)。

- 在标识符后键入 ?-Tab 时包含片段

   选择此选项后，IntelliSense 会在标识符后按 ?+Tab 时，将 C# 代码片段的别名添加到完成列表中

### <a name="enter-key-behavior"></a>输入关键行为

- 按下 Enter 时不添加新行

   指定在完成列表中选择项目以及按下 Enter 之后不自动添加新行。

- 只有在完整键入的单词结尾后按下回车键时才添加新行

   指定如果键入完成列表中某条目的所有字符后按 Enter，则自动添加新行并且光标移动到新行。

   例如，如果键入 `else` 后按 Enter，则编辑器中显示以下内容：

   `else`

   `|`（光标位置）

   但是，如果仅键入 `el`，然后按 Enter，则编辑器中显示以下内容：

   `else|`（光标位置）

- 按下 Enter 时始终添加新行

   指定如果键入完成列表中某条目的任意字符后按 Enter，则自动添加新行并且光标移动到新行。

## <a name="see-also"></a>请参阅

- [“选项”对话框 ->“环境”->“常规”](../../ide/reference/general-environment-options-dialog-box.md)
- [使用 IntelliSense](../../ide/using-intellisense.md)