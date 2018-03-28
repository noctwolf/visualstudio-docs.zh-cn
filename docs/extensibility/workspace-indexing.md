---
title: 索引在 Visual Studio 中的工作区 |Microsoft 文档
ms.custom: ''
ms.date: 02/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3163e98c-1c79-48a7-813f-7923be894ba1
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 9bf3a094184e2d57b4a066234d84a6ab6380510b
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="workspace-indexing"></a>工作区索引

在解决方案中，项目系统负责提供功能的生成、 调试**GoTo**搜索符号，，和的详细信息。 项目系统可以执行此工作，因为其了解的关系和功能在项目中的文件。 [打开文件夹](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)工作区需要相同的见解，从而提供丰富 IDE 功能。 集合和持久存储此数据是名为工作区中索引的过程。 可以通过一组异步 Api 查询此索引的数据。 扩展可以参与索引过程通过提供<xref:Microsoft.VisualStudio.Workspace.Indexing.IFileScanner>知道如何处理特定类型的文件的 s。

## <a name="types-of-indexed-data"></a>类型的索引的数据

有三种编制索引的数据。 请注意预期的方式从文件扫描程序的类型不同于从索引反序列化的类型。

|数据|文件扫描程序类型|索引查询结果类型|相关的类型|
|--|--|--|--|
|参考资料|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceInfo>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceResult>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceInfoType>|
|符号|<xref:Microsoft.VisualStudio.Workspace.Indexing.SymbolDefinition>|<xref:Microsoft.VisualStudio.Workspace.Indexing.SymbolDefinitionSearchResult>|<xref:Microsoft.VisualStudio.Workspace.Indexing.ISymbolService> 应使用而不是`IIndexWorkspaceService`查询|
|数据值|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileDataValue>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileDataResult`1>||

## <a name="querying-for-indexed-data"></a>查询索引的数据

有两个异步类型可用于访问持久的数据。 第一种是通过<xref:Microsoft.VisualStudio.Workspace.Indexing.IIndexWorkspaceData>。 它提供对单个文件的基本访问`FileReferenceResult`和`FileDataResult`数据，并缓存结果。 第二个是<xref:Microsoft.VisualStudio.Workspace.Indexing.IIndexWorkspaceService>它不使用缓存，但允许多个查询的功能。

```csharp
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Indexing;

private static IIndexWorkspaceData GetCachedIndexedData(IWorkspace workspace)
{
    // Gets access to indexed data wrapped in a cache.
    return workspace?.GetIndexWorkspaceDataService()?.CreateIndexWorkspaceData();
}

private static IIndexWorkspaceService GetDirectIndexedData(IWorkspace workspace)
{
    // Gets direct access to indexed data.
    // Can also be casted to IIndexWorkspaceService2.
    return workspace?.GetIndexWorkspaceService();
}
```

## <a name="participating-in-indexing"></a>参与索引

工作区中索引大致按照以下顺序进行：

1. 发现和文件系统中的实体 （仅在初始打开扫描） 的工作区的持久性。
1. 每个文件，具有最高优先级的匹配提供程序需要扫描`FileReferenceInfo`s。
1. 每个文件，具有最高优先级的匹配提供程序需要扫描`SymbolDefinition`s。
1. 每个文件，所有提供程序将要求`FileDataValue`s。

扩展可以通过实现导出扫描仪`IWorkspaceProviderFactory<IFileScanner>`和导出具有的类型<xref:Microsoft.VisualStudio.Workspace.Indexing.ExportFileScannerAttribute>。 `SupportedTypes`特性自变量应为一个或多个值从<xref:Microsoft.VisualStudio.Workspace.Indexing.FileScannerTypeConstants>。 有关示例扫描仪，请参阅 VS SDK[示例](https://github.com/Microsoft/VSSDK-Extensibility-Samples/blob/master/Open_Folder_Extensibility/C%23/SymbolScannerSample/TxtFileSymbolScanner.cs)。

> [!WARNING]
> 不导出文件扫描仪支持`FileScannerTypeConstants.FileScannerContentType`类型。 Microsoft 仅供内部使用，使用它。

在高级的情况下，扩展可能动态支持文件类型的任意一组。 而不是 MEF 导出`IWorkspaceProviderFactory<IFileScanner>`，扩展可以导出`IWorkspaceProviderFactory<IFileScannerProvider>`。 当索引开始时，此工厂类型将导入，实例化，并具有其<xref:Microsoft.VisualStudio.Workspace.Indexing.IFileScannerProvider.GetSymbolScannersAsync%2A>方法调用。 `IFileScanner` 支持的任何值的实例`FileScannerTpeConstants`将遵循，而不仅仅是符号。

## <a name="next-steps"></a>后续步骤

* [工作区和语言服务](workspace-language-services.md)-了解如何将语言服务集成到一个打开文件夹工作区。
* [工作区中生成](workspace-build.md)-打开文件夹支持生成系统例如 MSBuild 和生成文件。