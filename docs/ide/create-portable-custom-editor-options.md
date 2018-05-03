---
title: 在 Visual Studio 中使用 EditorConfig 设置
ms.date: 12/13/2017
ms.topic: conceptual
helpviewer_keywords:
- editorconfig [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.openlocfilehash: ff3391023d9a863bd9f06b4608b327902a17f0ac
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>使用 EditorConfig 创建可移植的自定义编辑器设置

在 Visual Studio 2017 中，可以向项目或基本代码添加 [EditorConfig](http://editorconfig.org/) 文件，强制对使用该基本代码的所有人实施一致的编码样式。 EditorConfig 设置优先于全局 Visual Studio 文本编辑器设置。 这意味着，可以调整每种基本代码，以使用特定于该项目的文本编辑器设置。 仍然可以在 Visual Studio“选项”对话框中设置个人编辑器首选项。 以下两种情况下将应用这些设置：每当在不具备 .editorconfig 文件的代码库中执行操作时，或者当 .editorconfig 文件不会替代特定设置时。 此类首选项的一个示例为缩进样式 &mdash; 制表符或空格。

许多代码编辑器和 IDE（包括 Visual Studio）都支持 EditorConfig 设置。 它是一种随代码移动的可移植组件，甚至可以在 Visual Studio 外强制实施编码样式。

> [!NOTE]
> 在 Visual Studio 中将 EditorConfig 文件添加到你的项目时，现有代码的格式设置不会更改，除非设置文档格式（“编辑” > “高级” > “设置文档格式”或 Ctrl+K，Ctrl+D）。 但任何新的代码行都将根据 EditorConfig 设置设置格式。

## <a name="coding-consistency"></a>编码一致性

EditorConfig 文件中的设置用于在基本代码库中维持一致的编码风格和设置，例如缩进样式、选项卡宽度、行尾字符以及编码等，而无需考虑使用的编辑器或 IDE。 例如，使用 C# 编码时，如果基本代码约定为始终缩进五个空格字符、文档使用 UTF-8 编码，且每一行始终以 CR/LF 结束，则可以配置 .editorconfig 文件达到此效果。

个人项目中使用的编码约定可能不同于团队项目使用的编码约定。 例如，你可能倾向在编码时，缩进操作会添加制表符。 但你的团队可能更倾向使用四个空格字符的缩进，而不是制表符。 EditorConfig 文件让你能对每个方案进行配置，从而解决这一问题。

由于这些设置包含在基本代码的文件中，因此能与基本代码一起移动。 只要在 EditorConfig 兼容的编辑器中打开代码文件，就能实现文本编辑器设置。 有关 EditorConfig 文件的详细信息，请参阅 [EditorConfig.org](http://editorconfig.org/) 网站。

## <a name="supported-settings"></a>支持的设置

Visual Studio 中的编辑器支持 [EditorConfig 属性](http://editorconfig.org/#supported-properties)的核心集：

- indent_style
- indent_size
- tab_width
- end\_of_line
- charset
- trim\_trailing_whitespace
- insert\_final_newline
- 根

所有 Visual Studio 支持的语言（XML 除外）均支持 EditorConfig 编辑器设置。 此外，EditorConfig 还支持适用于 C# 和 Visual Basic 的[代码样式](../ide/editorconfig-code-style-settings-reference.md)约定和[命名](../ide/editorconfig-naming-conventions.md)约定。

## <a name="adding-and-removing-editorconfig-files"></a>添加和删除 EditorConfig 文件

将 EditorConfig文件添加到项目或基本代码不会将现有样式转换为新样式。 例如，如果文件中存在制表符格式的缩进，并添加了以空格缩进的 EditorConfig 文件，则缩进字符不会自动转换为空格。 但任何新的代码行都将根据 EditorConfig 文件设置格式。 此外，如果设置文档格式（“编辑” > “高级” > “设置文档格式”或 Ctrl+K，Ctrl+D），则 EditorConfig 文件中的设置将应用到现有代码行。

如果从项目或基本代码库中删除 EditorConfig 文件，必须关闭并重新打开任何打开的代码文件才能还原到新代码行的全局编辑器设置。

### <a name="to-add-an-editorconfig-file-to-a-project-or-solution"></a>若要将 EditorConfig 文件添加到项目或解决方案

1. 在 Visual Studio 中打开项目或解决方案。 根据要应用 .editorconfig 设置的对象（是解决方案中的所有项目还是其中一个项目），选择项目或解决方案节点。 还可在项目或解决方案中选择一个文件夹，向其添加 .editorconfig 文件。

1. 从菜单栏中，选择“项目” > “添加新项...”，或按 Ctrl+Shift+A。

   此时将打开“添加新项”对话框。

1. 在左侧的类别，选择“常规”，然后选择“文本文件”模板。 在“名称”文本框中，输入 `.editorconfig`，然后选择“添加”。

   解决方案资源管理器中随即显示一个 .editorconfig 文件，且文件在编辑器中打开。

   ![解决方案资源管理器中的 .editorconfig 文件](media/editorconfig-in-solution-explorer.png)

1. 根据需要编辑文件，例如：

   ```EditorConfig
   root = true

   [*.{cs,vb}]
   indent_size = 4
   trim_trailing_whitespace = true

   [*.cs]
   csharp_new_line_before_open_brace = methods
   ```

或者，可安装 [EditorConfig 语言服务扩展](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig)。 安装此扩展后，仅需右键单击解决方案节点、项目节点或解决方案资源管理器中的任何文件夹，从出现的菜单中，或在这些节点或文件夹的上下文菜单中选择“添加” > “.editorconfig 文件”即可。

![添加带有文件扩展名的 .editorconfig 文件](media/editorconfig-extension-add.png)

## <a name="override-editorconfig-settings"></a>替代 EditorConfig 设置

如果将 .editorconfig 文件添加到文件层次结构中的某文件夹，则其设置将应用于该级别及更低级别的所有适用文件。 还可替代特定项目、代码库或部分代码库的 EditorConfig 设置，以使其使用与代码库其他部分不同的约定。 当要包含其他地方的代码而不想更改其约定时，这会很有用。

若要替代部分或全部 EditorConfig 设置，请在要应用这些替代设置的文件层次结构级别添加 .editorconfig 文件。 新的 EditorConfig 文件设置应用于同级目录和任何子目录中的文件。

![EditorConfig 层次结构](../ide/media/vside_editorconfig_hierarchy.png)

如果想替代一部分而非所有设置，请在 .editorconfig 文件中仅指定这些设置。 仅替代较低级别文件中显式列出的属性。 更高级别 .editorconfig 文件中的其他设置会继续应用。 如果要确保_任何_更高级别的 .editorconfig 文件中_没有_设置应用于此部分代码库，请将 ```root=true``` 属性添加到较低级别的 .editorconfig 文件中：

```EditorConfig
# top-most EditorConfig file
root = true
```

EditorConfig 文件从上到下进行读取，最近的 EditorConfig 文件会最后读取。 来自匹配 EditorConfig 部分的约定会按读取顺序进行应用，因此更近文件中的约定会优先使用。

## <a name="editing-editorconfig-files"></a>编辑 EditorConfig 文件

Visual Studio 提供 IntelliSense 完成列表，帮助你编辑 .editorconfig 文件。

![.editorconfig 文件中的 IntelliSense](media/editorconfig-intellisense-no-extension.png)

编辑 EditorConfig 文件后，必须重载代码文件，新设置才会生效。

如果编辑大量 .editorconfig 文件，可能会发现 [EditorConfig 语言服务](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig)扩展很有用。 该扩展的一些功能包括语法高亮显示、改进的 IntelliSense、验证和代码格式。

![带有 EditorConfig 语言服务扩展的 IntelliSense](media/editorconfig-intellisense.png)

## <a name="example"></a>示例

以下示例演示将 .editorconfig 文件添加到项目之前和之后 C# 代码片段的缩进状态。 Visual Studio 文本编辑器“选项”对话框中的“Tab”设置设置为按 Tab 键时可生成空格字符。

![文本编辑器 Tab 设置](../ide/media/vside_editorconfig_tabsetting.png)

按预期，在下一行按 **Tab** 键会使该行首行缩进四个空格字符。

![使用 EditorConfig 之前的代码](../ide/media/vside_editorconfig_before.png)

将具有以下内容的名为 .editorconfig 的新文件添加到项目。 `[*.cs]` 设置意味着此更改仅应用于项目中的 C# 代码文件。

```EditorConfig
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

这意味着如果目录结构中与项目位于相同位置或在项目之上的某个 EditorConfig 文件中指定了“工具” > “选项” > “文本编辑器”中的任何编辑器设置（如缩进尺寸和样式、制表符大小或编码约定），则 EditorConfig 文件中的约定会替代“选项”中的设置。 可以通过在“工具” > “选项” > “文本编辑器”中切换“遵循项目编码约定”选项来控制此行为。 取消选中该选项会关闭 Visual Studio 的 EditorConfig 支持。

![工具选项 - 遵循项目编码约定](media/coding_conventions_option.png)

还可以通过打开命令提示符并从包含项目的磁盘的根目录运行以下命令，在父目录中查找任何 .editorconfig 文件：

```Shell
dir .editorconfig /s
```

可以通过在存储库的根目录或项目所在目录的 .editorconfig 文件中设置 ```root=true``` 属性，控制 EditorConfig 约定的范围。 Visual Studio 会在打开的文件的目录和每个父目录中查找名为 .editorconfig 的文件。 到达根文件路径时或找到具有 ```root=true``` 的 .editorconfig 文件时搜索结束。

## <a name="see-also"></a>请参阅

- [.NET 代码样式约定](../ide/editorconfig-code-style-settings-reference.md)
- [.NET 命名约定](../ide/editorconfig-naming-conventions.md)
- [支持语言服务的 EditorConfig](../extensibility/supporting-editorconfig.md)
- [EditorConfig.org](http://editorconfig.org/)
- [在编辑器中编写代码](writing-code-in-the-code-and-text-editor.md)