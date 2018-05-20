---
title: EditorConfig
description: 使用 editorconfig 文件在 Visual Studio for Mac 中启用一致的项目编码样式。
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 26A0DE31-2FBF-4E1B-99FB-083111AA1680
ms.openlocfilehash: 336ec5ef0779bcd67302bea7b51851dced531a7d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="creating-and-editing-a-custom-editorconfig-file"></a>创建并编辑自定义 EditorConfig 文件

在 Visual Studio for Mac 中，可以向项目或基本代码添加 [EditorConfig](http://editorconfig.org/) 文件，强制对使用该基本代码的所有人实施一致的编码样式。 EditorConfig 文件中声明的设置优先于全局 Visual Studio 文本编辑器设置。 在项目或代码库中使用 EditorConfig 可为项目设置编码样式、首选项和警告。 这使所有 Visual Studio for Mac 用户都能更轻松地遵守项目的编码做法。

[EditorConfig](http://editorconfig.org/) 文件受到许多 IDE 和代码编辑器（包括 Visual Studio 2017）支持。 

## <a name="supported-settings"></a>支持的设置

Visual Studio 中的编辑器支持 [EditorConfig 属性](http://editorconfig.org/#supported-properties)的核心集：

- `indent_style`
- `indent_size`
- `tab_width`
- `end_of_line`
- `charset`
- `trim_trailing_whitespace`
- `insert_final_newline`
- `root`

EditorConfig 还支持 C# 中的[代码样式格式设置](https://docs.microsoft.com/visualstudio/ide/editorconfig-code-style-settings-reference)。

## <a name="add-an-editorconfig-file-to-a-project"></a>将 EditorConfig 文件添加到项目

### <a name="adding-a-new-editorconfig-file"></a>添加新的 EditorConfig 文件

1. 在 Visual Studio for Mac 中打开项目。 选择想要在其中添加文件的项目节点。

2. 选择项目节点后，转到“文件”>“新建文件…” 在菜单栏，打开“新建文件”对话框。

3. 选择“其他”>“空文本文件”并将其命名为 `.editorconfig`。 按“新建”创建文件并在编辑器中将其打开：

    ![“新文件”对话框](media/editorconfig-image1.png)

4. 编辑文件。 例如:

    ```EditorConfig
    # This file is the top-most EditorConfig file
    root = true

    # All Files
    [*]
    indent_style = space
    indent_size = 8
    insert_final_newline = false
    trim_trailing_whitespace = false

    [*.cs]
    csharp_new_line_before_open_brace = none
    ```

4. 添加文件不会自动更新设置。 若要从 `.editorconfig` 文件反映设置，请从菜单栏选择项目节点并选择“编辑”>“格式”>“设置文档格式”：

    ![设置文档格式菜单项](media/editorconfig-image2.png)

### <a name="adding-an-existing-editorconfig-file"></a>添加现有的 EditorConfig 文件

如果正在使用已包含 `.editorconfig` 文件的项目或解决方案，则无需执行任何操作即可应用设置。 任何新的代码行都将根据 EditorConfig 设置设置格式。 应注意，虽然 Visual Studio for Mac 将 `.editorconfig` 文件保留在解决方案级别，但由于以 `.` 开头的文件是 macOS 中的隐藏文件，因此它们可能不会显示在 solution pad 中。

可能想重复使用项目中现有的 `.editorconfig` 文件。 若要添加现有文件，首先需要显示查找器中的隐藏文件，方法是在终端输入以下命令：

```bash
$ defaults write com.apple.Finder AppleShowAllFiles true
$ killall Finder
```

显示 `.editorconfig` 文件后，将其拖动到项目节点中。 看到以下对话框时，选择“将文件复制到目录”选项并选择“确定”：

![设置文档格式菜单项](media/editorconfig-image3.png)

若要从 `.editorconfig` 文件反映设置，请从菜单栏选择项目节点并选择“编辑”>“设置格式”>“设置文档格式”。

## <a name="editing-an-editorconfig-file"></a>编辑 EditorConfig 文件

EditorConfig 文件使用简单的文件布局来指定设置，下面使用前一个示例来解释：


```EditorConfig
# This file is the top-most EditorConfig file
root = true

# All Files
[*]
indent_style = space
indent_size = 4
insert_final_newline = false
trim_trailing_whitespace = false

[*.cs]
csharp_new_line_before_open_brace = none
```

通过将 `root` 设置为 `true` 可把该文件标记为代码库中的最顶级文件，并忽略任何更高级的 `.editorconfig` 文件，如[替代 EditorConfig 设置](#override-editorconfig-settings)部分所述。

每个部分用方括号 ([ ]) 表示，并指定下列属性应涉及的文件类型的信息。

在以上示例中，一些设置应用于项目的所有文件，其他设置仅添加到 C# 文件。 以下屏幕截图显示应用 `.editorconfig` 设置之前以及之后的情况：

**之前**：

![应用 editorconfig 设置之前](media/editorconfig-image4.png)

**之后**：

![应用 editorconfig 设置之后](media/editorconfig-image5.png)

有关可用的 EditorConfig 设置的详细信息，请参阅 [EditorConfig 的 .NET 编码约定设置](https://docs.microsoft.com/visualstudio/ide/editorconfig-code-style-settings-reference)一文以及官方文档的[支持的属性](http://editorconfig.org/#supported-properties)部分。

## <a name="override-editorconfig-settings"></a>替代 EditorConfig 设置

每个解决方案可以具有一个以上的 `.editorconfig` 文件。 Visual Studio for Mac 在解决方案中从上到下读取 `.editorconfig` 文件，并在此过程中添加和替代设置。 这意味着 `.editorconfig` 中与正在编辑的文件最接近的设置将优先。 

如果要确保任何更高级别的 `.editorconfig` 文件中没有设置应用于此部分代码库，请将 `root=true` 属性添加到较低级别的 `.editorconfig` 文件顶部：

```EditorConfig
# top-most EditorConfig file
root = true
```