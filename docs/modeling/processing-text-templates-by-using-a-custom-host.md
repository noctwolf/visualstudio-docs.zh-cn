---
title: 使用自定义宿主处理文本模板
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e4546c75f424f5091a22e9acd6cceb72f5d8038c
ms.sourcegitcommit: ef828606e9758c7a42a2f0f777c57b2d39041ac3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "39567085"
---
# <a name="process-text-templates-by-using-a-custom-host"></a>使用自定义主机处理文本模板

*文本模板转换*过程将*文本模板*文件作为输入并生成一个文本文件作为输出。 从 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 扩展或安装有 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 的计算机上运行的独立应用程序，可以调用文本转换引擎。 但是，必须提供*文本模板化宿主*。 该类将模板连接到环境，查找资源（如程序集和包含文件），并处理输出和错误消息。

> [!TIP]
> 如果要编写将在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 内运行的包或扩展，请考虑使用文本模板化服务而不是编写您自己的主机。 有关详细信息，请参阅[VS 扩展中调用文本转换](../modeling/invoking-text-transformation-in-a-vs-extension.md)。

> [!NOTE]
> 不建议在服务器应用程序中使用文本模板转换。 除非是在单个线程中，否则不建议使用文本模板转换。 这是因为文本模板化引擎可以重用单个 AppDomain，以便转换、编译和执行模板。 转换的代码未被设计为线程安全的。 该引擎旨在按顺序处理文件，因为在设计时它们位于 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 项目中。
>
> 对于运行时应用程序，请考虑使用预处理的文本模板： 请参阅[使用 T4 文本模板的运行时文本生成](../modeling/run-time-text-generation-with-t4-text-templates.md)。

如果应用程序使用一组在编译时固定的模板，使用预处理文本模板会更为简单。 如果应用程序将在未安装 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 的计算机上运行，也可以使用该方法。 有关详细信息，请参阅[使用 T4 文本模板的运行时文本生成](../modeling/run-time-text-generation-with-t4-text-templates.md)。

## <a name="execute-a-text-template-in-your-application"></a>在你的应用程序中执行文本模板

若要执行文本模板，可以调用 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> 的 ProcessTemplate 方法。

```csharp
using Microsoft.VisualStudio.TextTemplating;
...
Engine engine = new Engine();
string output = engine.ProcessTemplate(templateString, host);
```

 应用程序必须找到并提供模板，并且必须处理输出。

 在 `host` 参数中，必须提供实现 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> 的类。 这是由引擎回调的。

 宿主必须能记录错误、解析对程序集和包含文件的引用、提供可在其中执行模板的应用程序域并为每条指令调用相应的处理器。

 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> 在中定义**由 Microsoft.VisualStudio.TextTemplating。\*。0 dll**，并<xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>中定义**Microsoft.VisualStudio.TextTemplating.Interfaces。\*。0 dll**。

## <a name="in-this-section"></a>本节内容
 [演练： 创建自定义文本模板宿主](../modeling/walkthrough-creating-a-custom-text-template-host.md)演示如何创建自定义文本模板宿主，从而使文本模板功能提供外部[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。

## <a name="reference"></a>参考
 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>

## <a name="related-sections"></a>相关章节

- [文本模板转换过程](../modeling/the-text-template-transformation-process.md)描述文本转换的工作方式，以及哪些部分你可以自定义。
- [创建自定义 T4 文本模板指令处理器](../modeling/creating-custom-t4-text-template-directive-processors.md)概述文本模板指令处理器。