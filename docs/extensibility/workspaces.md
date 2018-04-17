---
title: Visual Studio 中的工作区 |Microsoft 文档
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3489592a-dc0c-4cd3-9b08-cd367626980a
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 0230201677fd2422817ca1fbeab6679a424e5c05
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="workspaces"></a>工作区

工作区是 Visual Studio 如何表示的文件中的任何集合[打开文件夹](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)，并且由表示<xref:Microsoft.VisualStudio.Workspace.IWorkspace>类型。 其本身而言，工作区不了解的内容或与该文件夹中的文件相关的功能。 相反，它提供一组常规的功能和扩展的 Api 来生成和使用其他人可对操作的数据。 生成者由组成，通过[Managed Extensibility Framework](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (MEF) 使用各种导出属性。

## <a name="workspace-providers-and-services"></a>工作区提供程序和服务

工作区提供程序和服务提供的数据和功能对工作区的内容做出反应。 它们可能提供上下文的文件信息，在源代码文件中的符号或构建的功能。

这两个概念使用[工厂模式](https://en.wikipedia.org/wiki/Factory_method_pattern)并且通过由工作区的 MEF 导入。 所有导出特性都实现`IProviderMetadataBase`或`IWorkspaceServiceFactoryMetadata`，但存在扩展应将用于导出的类型的具体类型。

提供程序和服务之间的一个区别是其与工作区中的关系。 工作区可有许多提供程序特定的类型，但每个工作区中创建的特定类型的只有一个服务。 例如，工作区都有许多文件扫描程序提供程序，但工作区中每个工作区具有只有一个索引服务。

另一个主要区别在于使用提供程序和服务的数据。 工作区是出于几个原因从提供程序获取数据的入口点。 首先，提供程序通常会有一些窄组他们创建的数据。 数据可能会将 C# 源文件的符号或生成文件上下文_CMakeLists.txt_文件。 工作区将匹配到其元数据对齐与请求的提供程序的使用者的请求。 其次，某些情况下允许对于许多方案促成而其他的请求的提供程序使用提供程序具有高优先级。

与此相反，扩展可以获取的实例，并直接工作区与服务进行交互。 扩展方法`IWorkspace`可用于提供由 Visual Studio 中，如服务<xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetFileWatcherService%2A>。 你的扩展可能会提供对你的扩展中的组件或其他扩展以供使用的工作区服务。 使用者应使用<xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetServiceAsync%2A>或扩展方法提供有关`IWorkspace`类型。

>[!WARNING]
> 不能创作与 Visual Studio 冲突的服务。 它可能导致意外的问题。

## <a name="disposal-on-workspace-closure"></a>在工作区闭包处置

在工作区的闭包，扩展程序可能需要释放，但调用异步代码。 <xref:Microsoft.VisualStudio.Threading.IAsyncDisposable>界面，可使编写此代码轻松。

## <a name="related-types"></a>相关的类型

- <xref:Microsoft.VisualStudio.Workspace.IWorkspace> 是像打开文件夹打开工作区的中心实体。
- <xref:Microsoft.VisualStudio.Workspace.IWorkspaceProviderFactory`1> 创建每个实例化的工作区提供程序。
- <xref:Microsoft.VisualStudio.Workspace.IWorkspaceServiceFactory> 创建每个实例化的工作区的服务。
- <xref:Microsoft.VisualStudio.Threading.IAsyncDisposable> 应在提供程序和需要在处置期间运行异步代码的服务上实现。
- <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper> 提供用于访问的已知的服务或任意服务的帮助器方法。

## <a name="workspace-settings"></a>工作区设置

工作区具有<xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager>服务，其中包括对工作区的简单但功能强大的控制。 有关设置的基本概述，请参阅[自定义生成和调试任务](../ide/customize-build-and-debug-tasks-in-visual-studio.md)。

对于大多数设置`SettingsType`类型_.json_文件，如_VSWorkspaceSettings.json_和_tasks.vs.json_。

工作区设置的能力中心围绕"作用域"是只需在工作区中的路径。 当使用者调用<xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager.GetAggregatedSettings%2A>，包括请求的路径和类型的设置的所有作用域进行聚合。 范围聚合优先级是，如下所示：

1. "本地设置"，这通常是工作区根`.vs`目录。
1. 所请求的路径本身。
1. 请求的路径的父目录。
1. 所有进一步父目录，直到并包括工作区根。
1. "全局设置"，它是用户目录中。

结果是的一个实例<xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings>。 此对象保存为特定类型的设置，作为设置键名存储可以查询`string`。 <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings.GetProperty%2A>方法和<xref:Microsoft.VisualStudio.Workspace.Settings.WorkspaceSettingsExtensions>扩展方法需要调用方知道所请求的设置值的类型。 因为大多数设置文件将保留为_.json_文件，都将使用多调用`string`， `bool`， `int`，以及这些类型的数组。 也支持对象类型。 在这些情况下，你可以使用`IWorkspaceSettings`本身作为类型参数。 例如：

```json
{
  "intValue": 1,
  "stringValue": "s",
  "boolValue": true,
  "stringArray": [
    "s1",
    "s2"
  ],
  "nestedIWorkspaceSettings": {
    "nestedString": "ns"
  }
}
```

假定采用这些设置中用户的_VSWorkspaceSettings.json_，可作为访问数据：

```csharp
using System.Collections.Generic;
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Settings;

private static void ReadSettings(IWorkspace workspace)
{
    IWorkspaceSettingsManager settingsManager = workspace.GetSettingsManager();
    IWorkspaceSettings settings = settingsManager.GetAggregatedSettings(SettingsTypes.Generic);

    // result == WorkspaceSettingsResult.Success
    WorkspaceSettingsResult result = settings.GetProperty("intValue", out int intValue);
    result = settings.GetProperty("stringValue", out string stringValue);
    result = settings.GetProperty("boolValue", out bool boolValue);
    result = settings.GetProperty("stringArray", out string[] stringArray);
    result = settings.GetProperty("nestedIWorkspaceSettings", out IWorkspaceSettings nestedIWorkspaceSettings);
    result = nestedIWorkspaceSettings.GetProperty("nestedString", out string nestedString);

    // Extension method alternative using default values.
    int intValueOrDefault = settings.Property("intValue", /* default */ 42);

    // Missing key. result == WorkspaceSettingsResult.Undefined
    result = settings.GetProperty("missing", out string missing);

    // Wrong type for a key. result == WorkspaceSettingsResult.Error
    result = settings.GetProperty("intValue", out IWorkspaceSettings notSettings);

    // Special ability to union "stringArray" across all scopes.
    IEnumerable<string> allStringArray = settings.UnionPropertyArray<string>("stringArray");
}
```

>[!NOTE]
>这些设置 Api 是与中提供的 Api 不相关`Microsoft.VisualStudio.Settings`命名空间。 工作区设置是不可知的主机，然后使用特定于工作区中的设置文件或动态设置提供程序。

### <a name="providing-dynamic-settings"></a>提供动态设置

扩展可以提供<xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsProvider>s。 这些内存中提供程序允许扩展以添加设置或重写其他人。

导出`IWorkspaceSettingsProvider`不同于其他工作区提供程序。 不是工厂`IWorkspaceProviderFactory`并且没有任何特殊属性类型。 相反，实现<xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsProviderFactory>并用`[Export(typeof(IWorkspaceSettingsProviderFactory))]`。

```csharp
// Common workspace provider factory pattern
[ExportFeatureProvider(some, args, to, export)]
internal class MyProviderFactory : IWorkspaceProviderFactory<IFeatureProvider>
{
     IFeatureProvider CreateProvider(IWorkspace workspace) => new Provider(workspace);
}

// IWorkspaceSettingsProvider pattern
[Export(typeof(IWorkspaceSettingsProviderFactory))]
internal class MySettingsProviderFactory : IWorkspaceSettingsProviderFactory
{
    // 100 is typically the value used by built-in settings providers. Lower value is higher priority.
    int Priority => 100;

    IWorkspaceSettingsProvider CreateSettingsProvider(IWorkspace workspace) => new MySettingsProvider(workspace);
}
```

>[!TIP]
>实现返回的方法时`IWorkspaceSettingsSource`(如`IWorkspaceSettingsProvider.GetSingleSettings`)，返回的实例`IWorkspaceSettings`而非`IWorkspaceSettingsSource`。 `IWorkspaceSettings` 提供可在某些设置聚合期间的详细信息。

### <a name="settings-related-apis"></a>设置相关的 Api

- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager> 读取和聚合工作区中的设置。
- <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetSettingsManager%2A> 获取`IWorkspaceSettingsManager`工作区。
- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager.GetAggregatedSettings%2A> 获取给定范围聚合所有重叠的作用域的设置。
- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings> 包含特定范围的设置。

## <a name="workspace-suggested-practices"></a>工作区中建议的做法

- 返回从对象`IWorkspaceProviderFactory.CreateProvider`或类似的 Api，请记住其`Workspace`创建时的上下文。 应为此对象保留在创建编写提供程序接口。
- 保存特定工作区中的缓存或内工作区的"本地设置"路径的设置。 创建文件使用的路径`Microsoft.VisualStudio.Workspace.WorkspaceHelper.MakeRootedUnderWorkingFolder`在 Visual Studio 2017 15.6 或更高版本。 对于版本 15.6 之前的版本，使用下面的代码段：

```csharp
using System.IO;
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Settings;

private static string MakeRootedUnderWorkingFolder(IWorkspace workspace, string relativePath)
{
    string workingFolder = workspace.GetSettingsManager().GetAggregatedSettings(SettingsTypes.WorkspaceControlSettings).Property<string>("WorkingFolder");
    return Path.Combine(workingFolder, relativePath);
}
```

## <a name="solution-events-and-package-auto-load"></a>解决方案事件和包自动加载

加载的包可以实现`IVsSolutionEvents7`并调用`IVsSolution.AdviseSolutionEvents`。 它包括在打开和关闭 Visual Studio 中的文件夹上的事件。

UI 上下文可用来自动加载你的包。 该值为 `4646B819-1AE0-4E79-97F4-8A8176FDD664`。

## <a name="troubleshooting"></a>疑难解答

### <a name="the-sourceexplorerpackage-package-did-not-load-correctly"></a>SourceExplorerPackage 包未正确加载

工作区扩展性很大程度 MEF 基于，并且组合错误将导致承载打开的文件夹，无法加载的包。 例如，如果扩展将导出的类型`ExportFileContextProviderAttribute`，但该类型仅实现`IWorkspaceProviderFactory<IFileContextActionProvider>`，尝试在 Visual Studio 中打开文件夹时，将会出错。 错误详细信息可在_%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_id\ComponentModelCache\Microsoft.VisualStudio.Default.err_。 解决任何错误的类型由你的扩展实现。

## <a name="next-steps"></a>后续步骤

* [文件上下文](workspace-file-contexts.md)-文件上下文提供程序打开文件夹工作区使代码智能。 
* [索引](workspace-indexing.md)的工作区中索引收集和保留的工作区的信息。
