---
title: "在 VisualStudio 中使用 EditorConfig 设置 | Microsoft Docs"
ms.custom: 
ms.date: 10/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editorconfig [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 39b3228e64257552c8b629e421c9b5aa4f0e0931
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2017
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>使用 EditorConfig 创建可移植的自定义编辑器设置

Visual Studio 中的文本编辑器设置适用于给定类型的所有项目。 因此，如果更改 C# 文本编辑器设置，该设置也适用于 Visual Studio 中的所有 C# 项目。 但是，在某些情况下，可能需要使用不同于个人编辑器首选项的约定。 [EditorConfig](http://editorconfig.org/) 文件使你能够通过按每个项目描述常用的文本编辑器选项（如缩进大小），达到此目的。 EditorConfig 设置包含在与代码和项目文件共存的 .editorconfig 文件中，优先于全局 Visual Studio 文本编辑器设置。 这意味着，可以调整每种基本代码，以使用特定于该项目的文本编辑器设置。 在 Visual Studio 中使用此功能无需任何插件。

## <a name="coding-consistency"></a>编码一致性

EditorConfig 文件中的设置用于在基本代码库中维持一致的编码风格和设置，例如缩进样式、选项卡宽度、行尾字符以及编码等，而无需考虑使用的编辑器或 IDE。 例如，使用 C# 编码时，如果基本代码约定为始终缩进五个空格字符、文档使用 UTF-8 编码，且每一行始终以 CR/LF 结束，则可以配置 .editorconfig 文件达到此效果。

个人项目中使用的编码约定可能不同于团队项目使用的编码约定。 例如，你可能倾向在编码时，缩进操作会添加制表符。 但你的团队可能更倾向使用四个空格字符的缩进，而不是制表符。 EditorConfig 文件让你能对每个方案进行配置，从而解决这一问题。

由于这些设置包含在基本代码的文件中，因此能与基本代码一起移动。 只要在 EditorConfig 兼容的编辑器中打开代码文件，就能实现文本编辑器设置。 有关 EditorConfig 文件的详细信息，请参阅 [EditorConfig.org](http://editorconfig.org/) 网站。

## <a name="override-editorconfig-settings"></a>替代 EditorConfig 设置

如果在文件层次结构中将 .editorconfig 文件添加到文件夹，则其设置将应用于该级别和更低级别的所有适用文件。 若要替代特定项目或基本代码的 EditorConfig 设置，以便使用与顶级 EditorConfig 文件不同的约定，只需将 .editorconfig 文件添加到基本代码的存储库或项目目录的根目录即可。 确保将 ```root=true``` 属性放置在该文件中，以便 Visual Studio 不再在目录结构中继续向上查找任何 .editorconfig 文件。 新的 EditorConfig 文件设置将应用于同级目录和任何子目录中的文件。

```
# top-most EditorConfig file
root = true
```

![EditorConfig 层次结构](../ide/media/vside_editorconfig_hierarchy.png)

EditorConfig 文件从上到下进行读取，最近的 EditorConfig 文件会最后读取。 来自匹配 EditorConfig 部分的约定会按读取顺序进行应用，因此更近文件中的约定会优先使用。

## <a name="supported-settings"></a>支持的设置

Visual Studio 中的编辑器支持 [EditorConfig 属性](http://editorconfig.org/#supported-properties)核心集中的以下内容：

- indent_style
- indent_size
- tab_width
- end\_of_line
- charset
- 根

所有 Visual Studio 支持的语言（XML 除外）均支持 EditorConfig 编辑器设置。 此外，EditorConfig 还支持适用于 C# 和 Visual Basic 的[代码样式](../ide/editorconfig-code-style-settings-reference.md)约定和[命名](../ide/editorconfig-naming-conventions.md)约定。

## <a name="editing-editorconfig-files"></a>编辑 EditorConfig 文件

Visual Studio 提供一些 IntelliSense 用于编辑 .editorconfig 文件。 如果编辑大量 .editorconfig 文件，可能会发现 [EditorConfig 语言服务](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig)扩展很有用。

编辑 EditorConfig 文件后，必须重载代码文件，新设置才会生效。

## <a name="adding-and-removing-editorconfig-files"></a>添加和删除 EditorConfig 文件

将 EditorConfig文件添加到项目或基本代码不会将现有样式转换为新样式。 例如，如果文件中存在带制表符格式的缩进，并添加了以空格缩进的 EditorConfig 文件，则缩进字符将不会转换为空格。 但任何新的代码行将根据 EditorConfig 文件进行格式化。

如果从项目或基本代码库中删除 EditorConfig 文件，必须关闭并重新打开任何打开的代码文件才能还原到新代码行的全局编辑器设置。

## <a name="example"></a>示例

以下示例演示将 .editorconfig 文件添加到项目之前和之后 C# 代码片段的缩进状态。 Visual Studio 文本编辑器“选项”对话框中的“Tab”设置设置为按 Tab 键时可生成空格字符。

![文本编辑器 Tab 设置](../ide/media/vside_editorconfig_tabsetting.png)

按预期，在下一行按 **Tab** 键会使该行首行缩进四个空格字符。

![使用 EditorConfig 之前的代码](../ide/media/vside_editorconfig_before.png)

将具有以下内容的名为 .editorconfig 的新文件添加到项目。 `[*.cs]` 设置意味着此更改仅应用于此项目中的 C# 代码文件。

```
# Top-most EditorConfig file
root = true

# Tab indentation
[*.cs]
indent_style = tab
```

现在按 **Tab** 键时，会获得制表符而不是空格。

![使用 Tab 键添加制表符](../ide/media/vside_editorconfig_tab.png)

## <a name="troubleshooting-editorconfig-settings"></a>EditorConfig 设置疑难解答

如果在目录结构中处于或高于你项目所在位置的任何位置存在 EditorConfig 文件，则 Visual Studio 会将该文件中的编辑器设置应用于编辑器。 在这种情况下，可能会在状态栏中看到以下消息：

   “该项目编码约定覆盖了此文件类型的用户首选项”。

这意味着如果在某个 EditorConfig 文件中的“工具”、“选项”、“文本编辑器”中指定了任何编辑器设置（如缩进尺寸和样式、制表符大小或编码约定），且该文件在目录结构中位于与项目相同或高于项目的位置，则该文件中的约定会替代“选项”中的设置。 可以通过在“工具”、“选项”、“文本编辑器”中切换“遵循项目编码约定”选项，来控制此行为。 取消选中该选项会关闭 Visual Studio 的 EditorConfig 支持。

![工具选项 - 遵循项目编码约定](media/coding_conventions_option.png)

还可以通过打开命令提示符并从包含项目的磁盘的根目录运行以下命令，在父目录中查找任何 .editorconfig 文件：

```
dir .editorconfig /s
```

可以通过在存储库的根目录或项目所在目录的 .editorconfig 文件中设置 ```root=true``` 属性，控制 EditorConfig 约定的范围。 Visual Studio 会在打开的文件的目录和每个父目录中查找名为 .editorconfig 的文件。 如果到达根文件路径，或如果找到 ```root=true``` 的 .editorconfig 文件，则 Visual Studio 会停止搜索。

## <a name="see-also"></a>请参阅

[.NET 代码样式约定](../ide/editorconfig-code-style-settings-reference.md)  
[支持语言服务的 EditorConfig](../extensibility/supporting-editorconfig.md)  
[EditorConfig.org](http://editorconfig.org/)  
[在编辑器中编写代码](writing-code-in-the-code-and-text-editor.md)