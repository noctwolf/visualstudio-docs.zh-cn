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
ms.openlocfilehash: 16c92111fc29071447d4af5e736b881fa7c7a769
ms.sourcegitcommit: e680e8ac675f003ebcc8f8c86e27f54ff38da662
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "49356738"
---
# <a name="options-text-editor-c-advanced"></a>选项，文本编辑器，C#，高级

可使用“高级”选项页修改 C# 的编辑器格式设置、代码重构设置和 XML 文档注释设置。 要访问此选项页，请选择“工具” > “选项”，然后选择“文本编辑器” > “C#” > “高级”。

> [!NOTE]
> 并非所有选项都会在此处列出。

## <a name="analysis"></a>分析

- 启用完整解决方案分析

   针对解决方案中的所有文件启用代码分析，而不仅针对打开的代码文件。 详情请参阅[完整解决方案分析](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)。

## <a name="using-directives"></a>Using 指令

- 对 using 排序时将“System”指令排在第一位

   当你选择右键单击菜单中的“删除和排序 Using”命令后，它会对 `using` 指令进行排序，并将“System”命名空间置于列表顶部

   排序前：

   ```csharp
   using AutoMapper;
   using FluentValidation;
   using System.Collections.Generic;
   using System.Linq;
   using Newtonsoft.Json;
   using System;
   ```
   
   排序后：

   ```csharp
   using System;
   using System.Collections.Generic;
   using System.Linq;
   using AutoMapper;
   using FluentValidation;
   using Newtonsoft.Json;
   ```
   
- 单独的 using 指令组

   当你选择右键单击菜单中的“删除和排序 Using”命令后，它会在具有相同根命名空间的指令组之间插入空行，以将 `using` 指令分隔开来。

   排序前：

   ```csharp
   using AutoMapper;
   using FluentValidation;
   using System.Collections.Generic;
   using System.Linq;
   using Newtonsoft.Json;
   using System;
   ```
   
   排序后：
   
   ```csharp
   using AutoMapper;
   
   using FluentValidation;
   
   using Newtonsoft.Json;
   
   using System;
   using System.Collections.Generic;
   using System.Linq;
   ```
   
- 为引用程序集和 NuGet 包中的类型添加 using 

   选择[“快速操作”](../quick-actions.md)后，可使用它安装 NuGet 包，并为未引用的类型添加 `using` 指令。

   ![用于在 Visual Studio 中安装 NuGet 包的快速操作](media/nuget-lightbulb.png)
  
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
