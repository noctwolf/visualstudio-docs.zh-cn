---
title: Visual Studio 中的工作区文件上下文 |Microsoft 文档
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 7aaa0e65-f492-49ea-a845-35bd14910ca7
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: cdb013bb10c72041b03fce43e115806ecb3faeac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="workspace-file-contexts"></a>工作区文件上下文

所有深入[打开文件夹](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)工作区生成的"文件上下文提供程序"实现<xref:Microsoft.VisualStudio.Workspace.IFileContextProvider>接口。 这些扩展可能寻找文件夹中的模式或文件，读取 MSBuild 文件和生成文件，以便累积它们需要定义的文件上下文的见解检测包的依赖项，等等。 单独的文件上下文不执行任何操作，而是提供另一个扩展然后可以处理的数据。

每个<xref:Microsoft.VisualStudio.Workspace.FileContext>具有`Guid`与之关联的标识的数据类型它执行。 工作区中使用此`Guid`更高版本，以匹配它具有使用通过数据的扩展<xref:Microsoft.VisualStudio.Workspace.FileContext.Context>属性。 文件上下文提供程序使用的标识的文件上下文的元数据导出`Guid`s 其可能产生的数据。

定义后，文件上下文可以包含任意数量的文件或文件夹的工作区中相关联。 给定的文件或文件夹可能包含任意数量的文件上下文相关联。 它是多对多关系。

最常见的方案的文件上下文将与生成、 调试和语言服务。 有关详细信息，请参阅与这些方案相关的其他主题。

## <a name="file-context-lifecycle"></a>文件上下文生命周期

有关的生命周期`FileContext`是非确定性。 在任何时候，组件可以以异步方式请求为某些组上下文类型。 将查询提供程序支持的请求上下文类型某些子集。 `IWorkspace`实例充当中间人之间的使用者和提供程序通过<xref:Microsoft.VisualStudio.Workspace.IWorkspace.GetFileContextsAsync%2A>方法。 使用者可能会请求上下文，并执行一些短期操作根据上下文，而其他人可能请求上下文并维护的长生存期的引用。 

可能会导致文件上下文才能会过期的文件发生了更改。 提供程序可以在激发事件`FileContext`要通知的更新的客户。 例如，如果生成上下文提供一些文件，但磁盘上的更改使该上下文，原始的制造者可以调用此事件。 仍会引用的任何使用者`FileContext`然后可以为新 requery `FileContext`。

>[!NOTE]
>没有对使用者推送模型。 使用者将收不通知的提供程序的新`FileContext`后他们的请求。

## <a name="expensive-file-context-computations"></a>昂贵的文件上下文计算

从磁盘读取文件内容可能很昂贵，尤其是在提供程序需要解决文件之间的关系。 例如，对于某些源文件的文件上下文，可以查询提供程序，但文件上下文是依赖于从项目文件的元数据。 分析的项目文件或对其进行评估使用 MSBuild 将占用大量资源。 相反，扩展可以将导出`IFileScanner`创建`FileDataValue`在工作区中编制索引期间的数据。 现在当系统询问的文件上下文`IFileContextProvider`可以快速查询该索引的数据。 有关索引的详细信息，请参阅[工作区中索引](workspace-indexing.md)主题。

>[!WARNING]
>务必小心的其他方法，你`FileContext`可能成本来计算。 某些 UI 交互是同步的依赖于大量`FileContext`请求。 示例包括打开编辑器选项卡并打开**解决方案资源管理器**上下文菜单。 这些操作使类型请求的许多生成上下文。

## <a name="file-context-related-apis"></a>文件上下文相关 Api

- <xref:Microsoft.VisualStudio.Workspace.FileContext> 保存数据和元数据。
- <xref:Microsoft.VisualStudio.Workspace.IFileContextProvider> 和<xref:Microsoft.VisualStudio.Workspace.IFileContextProvider`1>创建的文件上下文。
- <xref:Microsoft.VisualStudio.Workspace.ExportFileContextProviderAttribute> 导出文件上下文提供程序。
- <xref:Microsoft.VisualStudio.Workspace.IWorkspace.GetFileContextsAsync%2A> 用于使用者来获取文件上下文。
- <xref:Microsoft.VisualStudio.Workspace.Build.BuildContextTypes> 定义将使用打开的文件夹的生成上下文类型。

## <a name="file-context-actions"></a>文件上下文操作

虽然`FileContext`本身是有关某些文件，只是数据<xref:Microsoft.VisualStudio.Workspace.IFileContextAction>是 express 和操作这些数据的方法。 `IFileContextAction` 是灵活中其使用情况。 两个及其最常见的用例是生成和调试。

## <a name="reporting-progress"></a>报告进度

<xref:Microsoft.VisualStudio.Workspace.IFileContextActionBase.ExecuteAsync%2A>方法传递`IProgress<IFileContextActionProgressUpdate>`，但参数不应使用为该类型。 `IFileContextActionProgressUpdate` 是一个空的接口，并且调用`IProgress<IFileContextActionProgressUpdate>.Report(IFileContextActionProgressUpdate)`可能引发`NotImplementedException`。 相反，`IFileContextAction`必须强制转换根据方案的另一种类型的自变量。

由 Visual Studio 提供的类型的信息，请参阅各自方案的文档。

## <a name="file-context-action-related-apis"></a>与 Api 相关的文件上下文操作

- <xref:Microsoft.VisualStudio.Workspace.IFileContextAction> 执行基于某些行为`FileContext`。
- <xref:Microsoft.VisualStudio.Workspace.IFileContextActionProvider> 创建的实例`IFileContextAction`。
- <xref:Microsoft.VisualStudio.Workspace.ExportFileContextActionProviderAttribute> 将类型导出`IWorkspaceProviderFactory<IFileContextActionProvider>`。

## <a name="file-watching"></a>文件监视

工作区侦听文件更改通知，并且提供<xref:Microsoft.VisualStudio.Workspace.IFileWatcherService>通过<xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetFileWatcherService%2A>。 匹配的"ExcludedItems"设置文件不会生成文件通知事件。 事件之间的阈值用于通知简化和重复的降低。 当你需要对文件更改做出响应时，你应订阅此服务。

>[!TIP]
>工作区[索引服务](workspace-indexing.md)订阅文件事件默认情况下。 文件添加和修改将导致相关`IFileScanner`的事件调用为该文件的新数据。 删除的文件将删除索引的数据。 无需订阅你`IFileScanner`到文件观察程序服务。

## <a name="next-steps"></a>后续步骤

* [索引](workspace-indexing.md)的工作区中索引收集和保留的工作区的信息。
* [工作区](workspaces.md)-查看工作区概念和设置存储。
