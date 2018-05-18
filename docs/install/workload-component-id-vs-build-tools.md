---
title: Visual Studio 生成工具 2017 工作负载和组件 ID
description: 使用 Visual Studio 工作负载和组件 ID 来构建基于 Windows 的经典应用程序
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 05/07/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: b99298df-0280-47fc-af73-44cd7a8ac553
ms.workload:
- multiple
ms.openlocfilehash: 8634017862a12b3a399f003d6f16c9689b7aaa20
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="visual-studio-build-tools-2017-component-directory"></a>Visual Studio 生成工具 2017 组件目录

本页的表中列出了可用于通过使用命令行安装 Visual Studio 或可指定为 VSIX 清单中的依赖项的 ID。 请注意，我们将在发布 Visual Studio 更新时添加其他组件。

另请注意以下有关本页的注意事项：

* 每个工作负载均有其自己的部分，后跟工作负载 ID 和适用于工作负载的组件表格。
* 默认情况下，安装工作负载时将安装**必需**组件。
* 如果愿意，还可以安装**推荐**和**可选**组件。
* 我们还添加了一个部分，此部分列出了不属于任何工作负载的其他组件。

在 VSIX 清单中设置依赖项时，必须仅指定组件 ID。 使用本页中的表格来确定最小组件依赖项。 在某些情况下，这可能意味着仅从工作负载指定一个组件。 在其他情况下，这可能意味着你从单个工作负载指定多个组件或从多个工作负载指定多个组件。 有关详细信息，请参阅[如何：将扩展性项目迁移到 Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) 页。

有关如何使用这些 ID 的详细信息，请参阅[使用命令行参数安装 Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) 页。 另外，有关其他产品的工作负载和组件 ID 的列表，请参阅 [Visual Studio 2017 工作负载和组件 ID](workload-and-component-ids.md) 页。

## <a name="azure-development-build-tools"></a>Azure 开发生成工具

**ID：** Microsoft.VisualStudio.Workload.AzureBuildTools

**说明：** 用于构建 Azure 应用程序的 MSBuild 任务和目标。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 目标包 | 15.6.27406.0 | 必需
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 开发工具 | 15.7.27520.0 | 必需
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 创作工具 | 15.0.26621.2 | 必需
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET 的 Azure 库 | 15.0.26208.0 | 必需
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Azure 云服务生成工具 | 15.7.27617.1 | 必需
Microsoft.VisualStudio.Component.DockerTools.BuildTools | 容器开发工具 - 生成工具 | 15.7.27617.1 | 必需
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 必需
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF 开发生成工具 | 15.6.27309.0 | 必需
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Web 开发生成工具 | 15.7.27604.0 | 必需
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 开发工具 | 15.6.27406.0 | 建议
Microsoft.Net.Core.Component.SDK | .NET Core 2.0 开发工具 | 15.6.27406.0 | 建议
Microsoft.VisualStudio.Component.AspNet45 | 高级 ASP.NET 功能 | 15.7.27625.0 | 建议
Microsoft.VisualStudio.Component.TypeScript.2.8 | TypeScript 2.8 SDK | 15.0.27617.1 | 建议
Microsoft.Net.Component.3.5.DeveloperTools | .NET Framework 3.5 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 开发工具 | 15.6.27406.0 | Optional

## <a name="net-desktop-build-tools"></a>.NET 桌面生成工具

**ID：** Microsoft.VisualStudio.Workload.ManagedDesktopBuildTools

**说明：** 用于使用 C#、Visual Basic 和 F# 生成 WPF、Windows 窗体和控制台应用程序的工具。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | 必需
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 目标包 | 15.6.27406.0 | 必需
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 必需
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 和 Visual Basic Roslyn 编译器 | 15.6.27309.0 | 必需
Microsoft.Component.ClickOnce.MSBuild | ClickOnce 生成工具 | 15.7.27617.1 | 建议
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 开发工具 | 15.6.27406.0 | 建议
Microsoft.Net.Core.Component.SDK | .NET Core 2.0 开发工具 | 15.6.27406.0 | 建议
Microsoft.VisualStudio.Component.TestTools.BuildTools | 测试工具核心功能 - 生成工具 | 15.7.27625.0 | 建议
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF 开发生成工具 | 15.6.27309.0 | 建议
Microsoft.Net.Component.3.5.DeveloperTools | .NET Framework 3.5 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.Core.Component.SDK.1x | .NET Core 1.0 - 1.1 开发工具 | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.FSharp.MSBuild | F# 编译器 | 15.7.27604.0 | Optional

## <a name="msbuild-tools"></a>MSBuild 工具

**ID：** Microsoft.VisualStudio.Workload.MSBuildTools

**说明：** 提供构建基于 MSBuild 的应用程序所需的工具。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | 必需
Microsoft.VisualStudio.Component.CoreBuildTools | Visual Studio 生成工具核心 | 15.6.27309.0 | 必需
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 和 Visual Basic Roslyn 编译器 | 15.6.27309.0 | 必需

## <a name="net-core-build-tools"></a>.NET Core 生成工具

**ID：** Microsoft.VisualStudio.Workload.NetCoreBuildTools

**说明：** 用于使用 .NET Core、ASP.NET Core、HTML/JavaScript 和容器生成应用程序的工具。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Net.Core.Component.SDK | .NET Core 2.0 开发工具 | 15.6.27406.0 | 必需
Microsoft.NetCore.BuildTools.ComponentGroup | .NET Core 生成工具 | 15.7.27617.1 | 必需
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 必需
Microsoft.Net.Core.Component.SDK.1x | .NET Core 1.0 - 1.1 开发工具 | 15.6.27406.0 | Optional

## <a name="nodejs-build-tools"></a>Node.js 生成工具

ID：Microsoft.VisualStudio.Workload.NodeBuildTools

**说明：** 使用 Node.js（事件驱动的异步 JavaScript 运行时）生成可扩展的网络应用程序。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Node.Build | Node.js 支持 | 15.6.27406.0 | 必需

## <a name="officesharepoint-build-tools"></a>Office/SharePoint 生成工具

**ID：** Microsoft.VisualStudio.Workload.OfficeBuildTools

**说明：** 生成 Office 和 SharePoint 加载项以及 VSTO 加载项。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Component.ClickOnce.MSBuild | ClickOnce 生成工具 | 15.7.27617.1 | 必需
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | 必需
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 目标包 | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 目标包 | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 目标包 | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 目标包 | 15.6.27406.0 | 必需
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 开发工具 | 15.7.27520.0 | 必需
Microsoft.VisualStudio.Component.NuGet | NuGet 程序包管理器 | 15.6.27309.0 | 必需
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 必需
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 和 Visual Basic Roslyn 编译器 | 15.6.27309.0 | 必需
Microsoft.VisualStudio.Component.Sharepoint.BuildTools | Office/SharePoint 开发生成工具 | 15.7.27617.1 | 必需
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF 开发生成工具 | 15.6.27309.0 | 必需
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Web 开发生成工具 | 15.7.27604.0 | 必需
Microsoft.VisualStudio.Component.TeamOffice.BuildTools | Visual Studio Tools for Office (VSTO) 生成工具 | 15.7.27617.1 | 建议
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 开发工具 | 15.6.27406.0 | Optional

## <a name="universal-windows-platform-build-tools"></a>通用 Windows 平台生成工具

**ID：** Microsoft.VisualStudio.Workload.UniversalBuildTools

**说明：** 提供生成通用 Windows 平台应用程序所需的工具。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | 必需
Microsoft.Component.NetFX.Native | .NET Native | 15.0.26208.0 | 必需
Microsoft.Component.VC.Runtime.OSSupport | 适用于 UWP 的 Visual C++ 运行时 | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | 必需
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 必需
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 和 Visual Basic Roslyn 编译器 | 15.6.27309.0 | 必需
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 静态分析工具 | 15.0.26208.0 | 必需
Microsoft.VisualStudio.Component.VC.Tools.ARM | 用于 ARM 的 Visual C++ 编译器和库 | 15.6.27406.0 | 必需
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 版本 15.7 v14.14 最新 v141 工具 | 15.7.27625.0 | 必需
Microsoft.VisualStudio.ComponentGroup.UWP.BuildTools | 通用 Windows 平台生成必备组件 | 15.7.27703.1 | 必需
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK (10.0.17134.0) | 15.7.27703.1 | 建议
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK (10.0.10240.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | 适用于 UWP 的 Windows 10 SDK (10.0.15063.0)：C#、VB 和 JS | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | 适用于 UWP 的 Windows 10 SDK (10.0.16299.0)：C#、VB 和 JS | 15.6.27406.0 | Optional

## <a name="visual-c-build-tools"></a>Visual C++ 生成工具

**ID：** Microsoft.VisualStudio.Workload.VCTools

说明：使用 Microsoft C++ 工具集、ATL 或 MFC 生成 Windows 桌面应用程序。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 静态分析工具 | 15.0.26208.0 | 必需
Microsoft.VisualStudio.Component.VC.CoreBuildTools | Visual C++ 生成工具的核心功能 | 15.6.27406.0 | 必需
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 Redistributable 更新 | 15.6.27406.0 | 必需
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 版本 15.7 v14.14 最新 v141 工具 | 15.7.27625.0 | 必需
Microsoft.VisualStudio.Component.Windows10SDK | Windows 通用 C 运行时 | 15.6.27406.0 | 必需
Microsoft.VisualStudio.Component.TestTools.BuildTools | 测试工具核心功能 - 生成工具 | 15.7.27625.0 | 建议
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK (10.0.17134.0) | 15.7.27703.1 | 建议
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 通用 CRT SDK | 15.6.27309.0 | Optional
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 目标包 | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.VC.140 | 适用于桌面的 VC++ 2015.3 v14.00 (v140) 工具集 | 15.7.27617.1 | Optional
Microsoft.VisualStudio.Component.VC.ATL | 用于 x86 和 x64 的 Visual C++ ATL | 15.7.27625.0 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | 用于 x86 和 x64 的 Visual C++ MFC | 15.7.27625.0 | Optional
Microsoft.VisualStudio.Component.VC.CLI.Support | C++/CLI 支持 | 15.6.27309.0 | Optional
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | 标准库模块（试验） | 15.6.27309.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM | 用于 ARM 的 Visual C++ 编译器和库 | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | 用于 ARM64 的 Visual C++ 编译器和库 | 15.6.27309.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK (10.0.10240.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | 适用于桌面 C++ [x86 和 x64] 的 Windows 10 SDK (10.0.15063.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | 适用于 UWP 的 Windows 10 SDK (10.0.15063.0)：C#、VB 和 JS | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | 适用于 UWP 的 Windows 10 SDK (10.0.15063.0)：C++ | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | 适用于桌面 C++ [x86 和 x64] 的 Windows 10 SDK (10.0.16299.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | 适用于 UWP 的 Windows 10 SDK (10.0.16299.0)：C#、VB 和 JS | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | 适用于 UWP 的 Windows 10 SDK (10.0.16299.0)：C++ | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.WinXP | 针对 C++ 的 Windows XP 支持 | 15.7.27703.1 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK 和 UCRT SDK | 15.6.27406.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | 针对 C++ 的 Windows XP 支持 | 15.7.27703.1 | Optional

## <a name="web-development-build-tools"></a>Web 开发生成工具

**ID：** Microsoft.VisualStudio.Workload.WebBuildTools

**说明：** 用于构建 Web 应用程序的 MSBuild 任务和目标。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 目标包 | 15.6.27406.0 | 必需
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 开发工具 | 15.7.27520.0 | 必需
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 必需
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Web 开发生成工具 | 15.7.27604.0 | 必需
Microsoft.Component.ClickOnce.MSBuild | ClickOnce 生成工具 | 15.7.27617.1 | 建议
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 目标包 | 15.6.27406.0 | 建议
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 开发工具 | 15.6.27406.0 | 建议
Microsoft.Net.Core.Component.SDK | .NET Core 2.0 开发工具 | 15.6.27406.0 | 建议
Microsoft.VisualStudio.Component.AspNet45 | 高级 ASP.NET 功能 | 15.7.27625.0 | 建议
Microsoft.VisualStudio.Component.DockerTools.BuildTools | 容器开发工具 - 生成工具 | 15.7.27617.1 | 建议
Microsoft.VisualStudio.Component.TestTools.BuildTools | 测试工具核心功能 - 生成工具 | 15.7.27625.0 | 建议
Microsoft.VisualStudio.Component.TypeScript.2.8 | TypeScript 2.8 SDK | 15.0.27617.1 | 建议
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF 开发生成工具 | 15.6.27309.0 | 建议
Microsoft.Net.Component.3.5.DeveloperTools | .NET Framework 3.5 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 目标包 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 开发工具 | 15.6.27406.0 | Optional
Microsoft.Net.Core.Component.SDK.1x | .NET Core 1.0 - 1.1 开发工具 | 15.6.27406.0 | Optional

## <a name="mobile-development-with-net"></a>使用 .NET 的移动开发

**ID：** Microsoft.VisualStudio.Workload.XamarinBuildTools

**说明：** 用于使用 C# 和 F# 生成 iOS、Android 和 Windows 版跨平台应用程序的工具。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | 必需
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | 必需
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 目标包 | 15.6.27406.0 | 必需
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 必需
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 和 Visual Basic Roslyn 编译器 | 15.6.27309.0 | 必需
Component.JavaJDK | Java SE 开发工具包 (8.0.1120.15) | 15.6.27406.0 | 建议
Component.Android.SDK25 | Android SDK 安装程序（API 级别 25） | 15.6.27413.0 | Optional

## <a name="unaffiliated-components"></a>独立组件

这些组件不随附于任何工作负载，但可选择作为单个组件。

组件 ID | name | 版本
--- | --- | ---
Microsoft.VisualStudio.Component.TypeScript.2.0 | TypeScript 2.0 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.1 | TypeScript 2.1 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.3 | TypeScript 2.3 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.5 | TypeScript 2.5 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27520.0
Microsoft.VisualStudio.Component.VC.ATL.ARM | Visual C++ ATL for ARM | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM.Spectre | 带有 Spectre 缓解措施的 Visual C++ ATL for ARM | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM64 | Visual C++ ATL for ARM64 | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM64.Spectre | 带有 Spectre 缓解措施的 Visual C++ ATL for ARM64 | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.Spectre | 带有 Spectre 缓解措施的 Visual C++ ATL (x86/x64) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATLMFC.Spectre | 带有 Spectre 缓解措施的 Visual C++ MFC for x86/x64 | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2（实验） | 15.7.27520.0
Microsoft.VisualStudio.Component.VC.MFC.ARM | Visual C++ MFC for ARM | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM.Spectre | 带有 Spectre 缓解措施的 Visual C++ MFC for ARM | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM64 | Visual C++ MFC for ARM64 | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM64.Spectre | 带有 Spectre 缓解措施的针对 ARM64 的 Visual C++ MFC 支持 | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.ARM.Spectre | 面向 Spectre 的 VC++ 2017 版本 15.7 v14.14 库 (ARM) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.ARM64.Spectre | 面向 Spectre 的 VC++ 2017 版本 15.7 v14.14 库 (ARM64) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.x86.x64.Spectre | 面向 Spectre 的 VC++ 2017 版本 15.7 v14.14 库 (x86 和 x64) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Tools.14.11 | VC++ 2017 版本 15.4 v14.11 工具集 | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.12 | VC++ 2017 版本 15.5 v14.12 工具集 | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.13 | VC++ 2017 版本 15.6 v14.13 工具集 | 15.0.27625.0

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [Visual Studio 工作负荷和组件 ID](workload-and-component-ids.md)
* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
* [使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
  * [命令行参数示例](command-line-parameter-examples.md)
* [创建 Visual Studio 的脱机安装](create-an-offline-installation-of-visual-studio.md)
