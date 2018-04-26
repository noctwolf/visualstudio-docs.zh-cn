---
title: 选项，文本编辑器，C#，高级
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
helpviewer_keywords:
- XML comments
- XML documentation, generating
- outlining options [C#]
- XML documentation, creating
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: a7675d711a4a1df6af4643a459f49b6ef518e5b4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="options-text-editor-c-advanced"></a>选项，文本编辑器，C#，高级

可使用“高级”选项页修改 C# 的编辑器格式设置、代码重构设置和 XML 文档注释设置。 要访问此选项页，请选择“工具” > “选项”，然后选择“文本编辑器” > “C#” > “高级”。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

## <a name="analysis"></a>分析

- 启用完整解决方案分析

   针对解决方案中的所有文件启用代码分析，而不仅针对打开的代码文件。 详情请参阅[完整解决方案分析](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)。

- 在外部进程中执行编辑器功能分析（实验）

## <a name="using-directives"></a>Using 指令

- 对 using 排序时将“System”指令排在第一位

- 单独的 using 指令组

- 建议对引用程序集中的类型使用 using

- 建议对 NuGet 包中的类型使用 using

## <a name="highlighting"></a>Highlighting

- 突出显示对光标下符号的引用

   光标定位在符号内，或单击某个符号时，将突出显示代码文件中该符号的所有实例。

- 突出显示光标下相关的关键字

## <a name="outlining"></a>大纲显示

- 打开文件时进入大纲模式

   选中后，会自动大纲显示代码文件，这将创建可折叠代码块。 首次打开文件时，#region 块和非活动代码块处于折叠状态。

- 显示过程行分隔符

- 显示声明级别构造的大纲

- 显示代码级别构造的大纲

- 显示注释和预处理器区域的大纲

- 折叠到定义时可折叠 #regions

## <a name="fading"></a>淡入淡出

- 淡出未使用的 using

- 淡出无法访问的代码

## <a name="block-structure-guides"></a>块结构指南

- 显示声明级别构造的指南

- 显示代码级别构造的指南

## <a name="editor-help"></a>编辑器帮助

- 为 /// 生成 XML 文档注释

   选中后，在键入 `///` 命令说明后为 XML 文档注释插入 XML 元素。 有关 XML 文档的详细信息，请参阅 [XML 文档注释（C# 编程指南）](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)。

- 编写 /\* \*/ 命令时，在新行的开头插入 \*

- 显示重命名跟踪的预览

- 输入时拆分字符串文本

- 报告“string.Format”调用中的无效占位符

## <a name="extract-method"></a>提取方法

- 不要在自定义结构上放置 ref 或 out

## <a name="implement-interface-or-abstract-class"></a>实现接口或抽象类

- 插入属性、事件和方法时，将其与同类型的其他元素放在一起或放在末尾

- 生成属性时，首选操作是引发属性或使用自动属性

## <a name="see-also"></a>请参阅

- [如何项文档生成项插入 XML 注释](../../ide/reference/generate-xml-documentation-comments.md)
- [XML 文档注释（C# 编程指南）](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
- [使用 XML 注释来记录代码（C# 指南）](/dotnet/csharp/codedoc)
- [设置语言特定的编辑器选项](../../ide/reference/setting-language-specific-editor-options.md)
- [C# IntelliSense](../../ide/visual-csharp-intellisense.md)