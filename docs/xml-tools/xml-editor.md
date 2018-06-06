---
title: XML 编辑器
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e2111286afde9e60391f1a7410fec2778b3ed673
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693781"
---
# <a name="xml-editor"></a>XML 编辑器

XML 编辑器基于 Visual Studio 文本编辑器中，并包含对 XML 语言的额外支持。 XML 编辑器包括以下功能：

- XML 1.0 语法检查。

- 键入时的架构验证。

- XML 代码段支持，包括从架构生成的代码段。

- 支持文档类型定义 (DTD)。

- 支持 XML 架构定义语言 (XSD) 架构。

- 从 XML 实例文档创建 XML 架构。

- 将 DTD 或 XML 数据简化 (XDR) 架构转换为 XML 架构。

- XSLT 1.0 语法检查。

- 文档以大纲方式显示，从而使得可以展开和折叠元素。

- 与集成[XML 架构资源管理器](../xml-tools/xml-schema-explorer.md)。 这提供 XML 架构的分层视图。

如的已知的文件扩展名调用 XML 编辑器 *.xml*， *.xsd*， *.xsl*，和 *.config*。如果文件似乎包含 XML，未知的文件扩展名也会调用“XML 编辑器”。 你也可以打开任何文件使用 XML 编辑器通过**打开**选项，并从列表中选择 XML 编辑器。

## <a name="xslt-intellisense"></a>XSLT IntelliSense

[通过 XSLT IntelliSense](../xml-tools/xml-editor-intellisense-features.md)可自动填充特性集名称、 模板模式和名称，并命名模板指定的模式或指定的参数名。

## <a name="xslt-profiler"></a>XSLT 探查器

[XSLT 探查器](../xml-tools/walkthrough-xslt-profiler.md)创建详细的 XSLT 性能报告，有助于度量、 评估和锁定 XSLT 代码中的与性能相关问题。 XSLT 探查器还包含有关 XSL 和 XSLT 样式表优化的有用提示。

## <a name="xslt-hierarchy"></a>XSLT 层次结构

[XSLT 层次结构工具](../xml-tools/walkthrough-using-xslt-hierarchy.md)，可在包含的样式表和/或内置模板规则中添加断点。

## <a name="see-also"></a>请参阅

- [代码编辑器的功能](../ide/writing-code-in-the-code-and-text-editor.md)提供有关文本编辑器的信息。
- [XML 标准参考](http://msdn.microsoft.com/79c78508-c9d0-423a-a00f-672e855de401)提供有关 XML 技术，包括 XML、 文档类型定义 (DTD)、 XML 架构定义语言 (XSD) 和 XSLT 的信息。
- [Visual Studio 中的 XML 工具](../xml-tools/xml-tools-in-visual-studio.md)