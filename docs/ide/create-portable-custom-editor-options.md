---
title: "使用 EditorConfig 创建可移植的自定义编辑器设置 | Microsoft Docs"
ms.custom: 
ms.date: 10/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editor
ms.assetid: 
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 2c1df6f8e34d2b8e72486dd804ba57f0dcf2406b
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>使用 EditorConfig 创建可移植的自定义编辑器设置
Visual Studio 中的文本编辑器设置适用于给定类型的所有项目。 因此，如果更改 C# 文本编辑器设置，该设置也适用于 Visual Studio 中的所有 C# 项目。 但是，在某些情况下，可能需要使用不同于个人编辑器首选项的约定。 [EditorConfig](http://editorconfig.org/) 文件基于每个项目提供常用的文本编辑器选项，可让你达到此目的。 EditorConfig 设置包含在已添加到代码库的.editorconfig 文件中，取代 Visual Studio 文本编辑器中的全局设置。 这意味着，可以调整每种基本代码，以使用喜欢的文本编辑器设置。 在 Visual Studio 中使用此功能无需任何插件。

## <a name="coding-consistency"></a>编码一致性
EditorConfig 文件中的设置用于维护某种语言一致的编码风格和设置，例如基本代码中的缩进样式、选项卡宽度、行尾字符以及编码等，而无需考虑使用的编辑器或 IDE。 例如，使用 C# 编码时，如果基本代码约定为始终缩进五个空格字符、文档使用 UTF-8 编码，且每一行始终以 CR/LF 结束，则可以配置 .editorconfig 文件达到此效果。

个人项目中使用的编码约定可能不同于团队项目使用的编码约定。 例如，你可能倾向在编码时按 Tab 键添加制表符。 但你的团队可能更倾向使用四个空格字符的缩进，而不是制表符。 EditorConfig 文件让你能对每个方案进行配置，从而解决这一问题。

由于这些设置包含在基本代码的文件中，因此能与基本代码一起移动。 只要在 EditorConfig 兼容的编辑器中打开代码文件，就能实现文本编辑器设置。 有关 EditorConfig 文件的详细信息，请参阅 [EditorConfig.org](http://editorconfig.org/) 网站。

## <a name="override-editorconfig-settings"></a>替代 EditorConfig 设置
如果在文件层次结构中将 .editorconfig 文件添加到文件夹，则其设置将应用于该级别和更低级别的所有适用文件。 若要替代特定项目或基本代码的 EditorConfig 设置，以便使用与顶级 .editorconfig 文件不同的约定，只需将 .editorconfig 文件添加到基本代码的存储库或项目目录的根目录即可。 确保将 ```root=true``` 属性放置在该文件中，以便 Visual Studio 不在目录结构中继续向上查找任何 .editorconfig 文件。 新的 .editorconfig 文件设置将应用于其所在级别和任何子目录中的文件。

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
- end_of_line
- charset
- 根

此外，它支持 [.NET 代码样式约定](../ide/editorconfig-code-style-settings-reference.md)。  

所有 Visual Studio 支持的语言（XML 除外）均支持 EditorConfig 设置。

## <a name="intellisense"></a>IntelliSense
Visual Studio 提供有限的 IntelliSense 用于编辑 .editorconfig 文件。 如果编辑大量 .editorconfig 文件，可能会发现 [EditorConfig 语言服务](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig)扩展很有用。

## <a name="example"></a>示例
以下示例演示将 .editorconfig 文件添加到项目之前和之后 C# 代码片段的缩进状态。 Visual Studio 文本编辑器“选项”对话框中的“Tab”设置设置为在代码中按 **Tab** 键时可生成空格字符。

![文本编辑器 Tab 设置](../ide/media/vside_editorconfig_tabsetting.png)

按预期，在下一行按 **Tab** 键会使该行首行缩进四个空格字符。

![使用 EditorConfig 之前的代码](../ide/media/vside_editorconfig_before.png)

将具有以下内容的名为 .editorconfig 的新文件添加到项目。 `[*.cs]` 设置意味着此更改仅应用于此项目中的 .cs 文件。  

![已将 .editorconfig 文件添加到项目](../ide/media/vside_editorconfig_addconfig.png)

现在按 **Tab** 键时，会获得制表符而不是空格。

![使用 Tab 添加制表符](../ide/media/vside_editorconfig_tab.png)

> [!NOTE]
>  将 .editorconfig 文件添加到项目或基本代码不会将现有样式转换为新样式，而仅应用于新添加的行。 如果从项目或基本代码删除 .editorconfig 文件，必须重新加载编辑器设置的代码文件，还原为全局设置。 在 Visual studio 中，.editorconfig 文件中的任何错误都会报告在“错误列表”窗口。

## <a name="troubleshooting-editorconfig-settings"></a>EditorConfig 设置疑难解答
如果在目录结构中处于或高于你项目所在位置的任何位置存在 EditorConfig 文件，则 Visual Studio 会将该文件中的编辑器设置应用于编辑器。 在这种情况下，可能会在状态栏中看到以下消息：

“该项目编码约定覆盖了此文件类型的用户首选项”。

这意味着如果在目录结构中处于或高于项目所在位置的 EditorConfig 文件中指定了“工具”、“选项”、“文本编辑器”中的任何编辑器设置（如缩进大小、制表符大小、缩进样式 &mdash; 制表符或空格，或编码约定，如 `var` 的使用），则该 EditorConfig 文件中的约定会替代“选项”中的设置。 可以通过在“工具”、“选项”、“文本编辑器”中切换“遵循项目编码约定”选项，来控制此行为。 取消选中该选项会关闭 Visual Studio 的 EditorConfig 支持。

![工具选项 - 遵循项目编码约定](media/coding_conventions_option.png)

还可以通过打开命令提示符并从包含项目的磁盘的根目录运行以下命令，在父目录中查找 .editorconfig 文件：

```
dir .editorconfig /s
```

可以通过在存储库的根目录或项目所在目录的 .editorconfig 文件中设置 ```root=true``` 属性，控制 EditorConfig 约定的范围。 Visual Studio 会在打开的文件的目录和每个父目录中查找名为 .editorconfig 的文件。 如果到达根文件路径，或如果找到 ```root=true``` 的 .editorconfig 文件，则 Visual Studio 会停止搜索。

## <a name="support-editorconfig-for-your-language-service"></a>支持语言服务的 EditorConfig
在大多数情况下，实现 Visual Studio 语言服务时，无需任何其他工作即可支持 EditorConfig 通用属性。 当用户打开文件时，核心编辑器将自动发现并读取 .editorconfig 文件，并设置相应的文本缓冲区和视图选项。 但是，用户编辑或设置文本格式时，某些语言服务将选择使用相应的上下文文本视图选项，而不是对制表符和空格等项使用全局设置。 在这些情况下，必须更新语言服务以支持 EditorConfig 文件。

以下是更新语言服务以支持 EditorConfig 文件所需的更改（通过将全局_特定语言_ 的选项替换为_上下文_ 选项）：  

### <a name="indent-style"></a>缩进样式
将：  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs  
 _或_   
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs  

替换为：  

!textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)  
 _或_   
!textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)  

### <a name="indent-size"></a>缩进大小
将：  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize  
 _或_   
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize  

替换为：  

textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)  
 _或_   
textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)  

### <a name="tab-size"></a>制表符大小
将：  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize  
 _或_   
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize  

替换为：  

textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)  
 _或_   
textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)  

## <a name="see-also"></a>请参阅
[.NET 代码样式约定](../ide/editorconfig-code-style-settings-reference.md)  
[EditorConfig.org](http://editorconfig.org/)  
[在编辑器中编写代码](writing-code-in-the-code-and-text-editor.md)