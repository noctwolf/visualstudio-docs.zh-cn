---
title: 选项，文本编辑器，C#，高级
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: ab08de0c6993f57c719f69ccf27e30e3cbe41c32
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433297"
---
# <a name="options-text-editor-c-advanced"></a>选项，文本编辑器，C#，高级

可使用“高级”选项页修改 C# 的编辑器格式设置、代码重构设置和 XML 文档注释设置。 要访问此选项页，请选择“工具” > “选项”，然后选择“文本编辑器” > “C#” > “高级”。

> [!NOTE]
> 并非所有选项都会在此处列出。

## <a name="analysis"></a>分析

- 启用完整解决方案分析

   针对解决方案中的所有文件启用代码分析，而不仅针对打开的代码文件。 详情请参阅[完整解决方案分析](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)。

## <a name="highlighting"></a>Highlighting

- 突出显示对光标下符号的引用

   光标定位在符号内，或单击某个符号时，将突出显示代码文件中该符号的所有实例。

## <a name="outlining"></a>大纲显示

- 打开文件时进入大纲模式

   选中后，会自动大纲显示代码文件，这将创建可折叠代码块。 首次打开文件时，#region 块和非活动代码块处于折叠状态。

## <a name="editor-help"></a>编辑器帮助

- 为 /// 生成 XML 文档注释

   选中后，在键入 `///` 命令说明后为 XML 文档注释插入 XML 元素。 有关 XML 文档的详细信息，请参阅 [XML 文档注释（C# 编程指南）](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)。

## <a name="see-also"></a>请参阅

- [如何项文档生成项插入 XML 注释](../../ide/reference/generate-xml-documentation-comments.md)
- [XML 文档注释（C# 编程指南）](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
- [使用 XML 注释记录代码（C# 指南）](/dotnet/csharp/codedoc)
- [设置语言特定的编辑器选项](../../ide/reference/setting-language-specific-editor-options.md)
- [C# IntelliSense](../../ide/visual-csharp-intellisense.md)