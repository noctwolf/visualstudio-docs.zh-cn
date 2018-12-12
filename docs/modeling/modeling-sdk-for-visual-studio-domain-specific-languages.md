---
title: Visual Studio 的建模 SDK - 特定于域的语言
titleSuffix: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6de309ca6ff9c1813a2a2a6ebc54ea6baa3a795f
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53060473"
---
# <a name="modeling-sdk-for-visual-studio---domain-specific-languages"></a>Visual Studio 的建模 SDK - 特定于域的语言

通过使用针对 Visual Studio 的建模 SDK，可以创建功能强大的基于模型的开发工具，您可以将它们集成到 Visual Studio。 同样，你可以创建一个或多个模型定义并将其集成到工具集中。

MSDK 的核心是你创建的用于表示业务领域内概念的模型的定义。 您可围绕具有各种工具，如关系图视图、 生成代码和其他项目，用于转换该模型的命令的功能和能力与代码和 Visual Studio 中的其他对象进行交互的模型。 在开发模型时，你可以将其与其他模型和工具结合以形成一个以开发为中心的功能强大的工具集。

MSDK 允许你以域特定语言 (DSL) 的形式快速开发模型。 首先使用专用编辑器来将架构或抽象语法与图形表示法一起定义。 根据此定义，VMSDK 将生成：

- 使用运行于基于事务的存储内的强类型 API 的模型实现。

- 一个基于树的资源管理器。

- 一个图形编辑器，用户可在其中查看你定义的模型或其各个部分。

- 以可读的 XML 形式保存模型的序列化方法。

- 使用文本模板化生成程序代码和其他项目的设施。

你可以自定义和扩展所有这些功能。 你的扩展以某种方式集成，以使你仍能更新 DSL 定义并重新生成功能而不丢失扩展。

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

[相关的博客文章](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)

高级的技术和故障排除指导，请访问[Visual Studio DSL 和建模工具扩展性论坛](http://go.microsoft.com/fwlink/?LinkID=186074)。

## <a name="in-this-section"></a>本节内容
 [域特定语言入门](../modeling/getting-started-with-domain-specific-languages.md)

 [了解模型、类和关系](../modeling/understanding-models-classes-and-relationships.md)

 [如何定义域特定语言](../modeling/how-to-define-a-domain-specific-language.md)

 [自定义和扩展域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)

 [域特定语言中的验证](../modeling/validation-in-a-domain-specific-language.md)

 [编写代码以自定义域特定语言](../modeling/writing-code-to-customise-a-domain-specific-language.md)

 [从域特定语言生成代码](../modeling/generating-code-from-a-domain-specific-language.md)

 [了解 DSL 代码](../modeling/understanding-the-dsl-code.md)

 [自定义文件存储和 XML 序列化](../modeling/customizing-file-storage-and-xml-serialization.md)

 [部署域特定语言解决方案](../modeling/deploying-domain-specific-language-solutions.md)

 [创建基于 Windows 窗体的域特定语言](../modeling/creating-a-windows-forms-based-domain-specific-language.md)

 [创建基于 WPF 的域特定语言](../modeling/creating-a-wpf-based-domain-specific-language.md)

 [如何：扩展域特定语言设计器](../modeling/how-to-extend-the-domain-specific-language-designer.md)

 [可视化和建模 SDK 支持的 Visual Studio 版本](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md)

 [如何：将域特定语言迁移至新版本](../modeling/how-to-migrate-a-domain-specific-language-to-a-new-version.md)

 [Visual Studio 的建模 SDK 的 API 参考](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
