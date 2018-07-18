---
title: 工作区和 Visual Studio 中的语言服务 |Microsoft 文档
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 8631ffea-83c8-4fd4-a01e-c59772e89c84
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 551a621ab97c232970d6ef67da14379c5cdfbd46
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140802"
---
# <a name="workspaces-and-language-services"></a>工作区和语言服务

语言服务可以提供[打开文件夹](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)用户相同的丰富的语言功能它们是用于在使用解决方案和项目。 语言服务可能自激活基于文件扩展名或打开文档的内容，但是此"松散文件"语言服务仅限于语法突出显示。 需要更多信息才能编辑/查看源代码时提供更丰富的体验。 每个语言服务都有自身的 API 用于初始化此文档的额外的上下文数据。 这通常是由紧密耦合同时向该语言服务和生成系统的项目系统进行管理。

## <a name="initialization"></a>初始化

在[工作区](workspaces.md)，语言服务初始化由<xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider>扩展点，它们仅在该语言服务专用化，并且知道执行任何操作生成创作。 这种方式，语言服务所有者可以维护单个打开文件夹在文件夹和文件 （例如 MSBuild，生成文件等） 在生成期间运行其编译器中存在多少模式任何扩展。 当文件已从中创建的文件上下文在磁盘上更改和刷新的文件上下文时，语言服务提供商将通知的更新的文件上下文集。 语言服务提供商可以更新其模型。

当在编辑器中打开文档时，Visual Studio 只考虑语言服务提供程序需要可以为其找到匹配的文件上下文提供程序的文件上下文类型。 然后将传递文件上下文从匹配的提供程序到所选的语言服务提供商通过`ILangaugeServiceProvider.InitializeAsync`。 语言服务提供程序如何处理文件的上下文数据是实现详细信息语言服务提供程序，但预期的用户体验是一种更丰富的语言服务为此打开文档。

## <a name="using-ilanguageserviceprovider"></a>使用 ILanguageServiceProvider

当使用创建的文件上下文时，将通知语言服务`ContextType`之一匹配`SupportedContextTypes`值语言服务器导出的属性。

若要支持语言服务，将需要扩展：

- 唯一`Guid`。 这将用于`SupportedContextTypes`特性自变量并在`FileContext`对象。
- 语言文件上下文
  - 提供程序工厂
    - `ExportFileContextProviderAttribute` 具有上述属性生成的唯一`Guid`中 `SupportedContextTypes`
    - 实现 `IWorkspaceProviderFactory<IFileContextProvider>`
  - 提供程序实现 `IFileContextProvider.GetContextsForFileAsync`
    - 构造一个新`FileContext`与`contextType`作为唯一生成的构造函数参数 `Guid`
    - 使用`Context`属性`FileContext`为提供的其他数据 `ILanguageServiceProvider`
- 语言服务
  - 提供程序工厂
    - `ExportLanguageServiceProvider` 具有上述属性生成的唯一`Guid`中 `SupportedContextTypes`
    - 实现 `IWorkspaceProviderFactory<ILanguageServiceProvider>`
  - 提供程序
    - 实现 `ILanguageServiceProvider`
    - 使用`ILanguageServiceProvider.InitializeAsync`以便在打开文件时提供的自变量的语言服务
    - 使用`ILanguageServiceProvider.UninitializeAsync`禁用关闭文件时提供的自变量的语言服务

>[!WARNING]
>`ILanguageServiceProvider`可能由主线程上工作区中调用方法。 请考虑计划在另一个线程以避免引入 UI 将延迟的工作。

## <a name="language-server-protocol"></a>语言服务器协议

`Microsoft.VisualStudio.Workspace.*` Api 不启用打开文件夹中的语言服务的唯一方法。 另一个选项是使用语言服务器。 详细信息，请阅读有关[语言服务器协议](language-server-protocol.md)。

## <a name="related-interfaces"></a>相关的接口

- <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> 匹配的文件类型的文件打开或关闭以进行编辑时调用。

## <a name="next-steps"></a>后续步骤

* [工作区中生成](workspace-build.md)-打开文件夹支持生成系统例如 MSBuild 和生成文件。 