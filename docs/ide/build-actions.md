---
title: 文件生成操作
ms.date: 11/19/2018
ms.technology: vs-ide-compile
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7820cbbe0477000c2a822e94f5204906d65025fa
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55950703"
---
# <a name="build-actions"></a>生成操作

Visual Studio 项目中的所有文件都具有生成操作。 生成操作控制编译项目时文件发生的情况。

> [!NOTE]
> 本主题适用于 Visual Studio  Windows 版。 对于 Visual Studio for Mac，请参阅 [Visual Studio for Mac 中的生成操作](/visualstudio/mac/build-actions)。

## <a name="set-a-build-action"></a>设置生成操作

若要设置文件的生成操作，通过选择“解决方案资源管理器”中的文件并按 Alt+Enter，在“属性”窗口中打开文件的属性。 或者，右键单击“解决方案资源管理器”中的文件，然后选择“属性”。 在“属性”窗口的“高级”部分下，使用“生成操作”旁边的下拉列表为文件设置生成操作。

![Visual Studio 中的文件生成操作](media/build-actions.png)

## <a name="build-action-values"></a>生成操作值

C# 和 Visual Basic 项目文件的一些生成操作如下所示：

* **无** - 文件不以任何方式生成。 例如，此值可用于文档文件，例如“ReadMe”文件。
* **编译** - 文件被传递到编译器作为源文件。
* **内容** - 标记为“内容”的文件可以通过调用 <xref:System.Windows.Application.GetContentStream%2A?displayProperty=nameWithType> 作为流进行检索。 对于 ASP.NET 项目，在部署站点时包含这些文件，作为站点的一部分。
* **嵌入式资源** - 文件被传递到 C# 编译器作为嵌入程序集中的资源。 可以调用 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A?displayProperty=fullName> 从程序集中读取文件。
* **AdditionalFiles** - 作为输入传递给 C# 或 Visual Basic 编译器的非源文本文件。 此生成操作主要用于向[分析器](../code-quality/roslyn-analyzers-overview.md)提供输入，项目引用这些分析器来验证代码质量。 有关详细信息，请参阅[使用其他文件](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Using%20Additional%20Files.md)。

## <a name="see-also"></a>请参阅

- [C# 编译器选项](/dotnet/csharp/language-reference/compiler-options/listed-alphabetically)
- [Visual Basic 编译器选项](/dotnet/visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically)
- [生成操作 (Visual Studio for Mac)](/visualstudio/mac/build-actions)