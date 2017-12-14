---
redirect_url: /visualstudio/ide/optimize-visual-studio-startup-time/
ms.openlocfilehash: 6ba351d5b395caaddd12021b09f8792cd19b2905
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
title: "在 Visual Studio 中优化解决方案加载 | Microsoft Docs" ms.custom: "" ms.date: 08/31/2017 ms.reviewer: "" ms.suite: "" ms.tgt_pltfrm: "" ms.topic: "article" helpviewer_keywords: 
  - "启动时间 [Visual Studio]"
  - "优化启动时间 [Visual Studio]"
  - "加快启动时间 [Visual Studio]" ms.assetid: 84989983-84bc-4f81-97a8-2131e3a25138 caps.latest.revision: 4 author: "gewarren" ms.author: "gewarren" manager: ghogen f1_keywords: 
  - "vs.performancecenter" ms.technology: 
  - "vs-ide-general"
---
# <a name="optimize-solution-loading-in-visual-studio"></a>在 Visual Studio 中优化解决方案加载
很多解决方案包含大量的项目，这会影响加载这些解决方案所用的时间。 但是，在团队环境中，开发人员通常会处理这些项目的不同子集，无需加载所有的单独项目。

Visual Studio 2017 支持轻量级解决方案加载。 启用轻量级解决方案加载 (LSL) 模式后，Visual Studio 2017 会加载大型解决方案中项目的一个小子集，而不会加载所有项目。 大部分的常用 IDE 功能在 LSL 模式下工作，借助这些功能，可以对整个解决方案进行生成、搜索和调试。 （LSL 模式下不支持的功能主要是“编辑并继续”。）  

> [!NOTE]
> 此内容适用于 Visual Studio 2017 Update 3

对于包括 30 多个项目的大型解决方案，LSL 通常会快速地加载两次解决方案（平均而言）。 尽管大部分 IDE 功能在 LSL 模式下工作，但某些 IDE 功能可能要求加载所有项目。 在这些情况下，Visual Studio 会自动加载整个解决方案，以便用户使用该功能。 在最坏的情况下，最终会在轻量级模式下加载所有项目。 

如果对当前未加载的项目使用 IDE 功能，则 Visual Studio 会为你加载相应的项目。 例如，尝试为未打开的项目创建或打开一个类图时，Visual Studio 会自动加载相应的项目。 详细的功能列表会在以下各节中引用。

以下各节说明如何启用轻量级解决方案加载，还可帮助你确定是否启用该功能。

## <a name="enable-or-disable-lightweight-solution-load"></a>启用或禁用轻型解决方案加载

可以右键单击“解决方案资源管理器”中的解决方案名称，并选择“启用轻型解决方案加载”。 选择此选项后，需要关闭并重新打开解决方案，才能激活轻型解决方案加载。

> [!NOTE]
> 类似的步骤适用于禁用 LSL。 若要禁用轻量级解决方案加载，请选择“禁用轻量级解决方案加载”，然后关闭并重新打开解决方案。 

![“解决方案资源管理器”](../ide/media/VSIDE_LSL_Solution_Setting.png)

## <a name="global_solution_load_settings"></a>配置轻量级解决方案加载的全局设置

可以全局禁用或配置所有解决方案的 LSL，方法是选择“工具”>“选项”>“项目和解决方案”。

![“工具选项”对话框](../ide/media/VSIDE_LightweightSolutionLoad.png)

## <a name="how-does-lightweight-solution-load-work-behind-the-scenes"></a>轻量级解决方案加载在后台如何工作？

加载解决方案时，Visual Studio 会记住之前打开的项目，并且会只加载这些项目。 所有其他项目在解决方案资源管理器中可见，但不会加载。 展开一个项目或右键单击一个项目后，Visual Studio 自动加载该项目。 自动加载项目所用的时间通常少于一秒，但对某些项目来说，会花费更长时间。 但是，Visual Studio 会启用搜索、调试、生成和源代码管理等在整个解决方案中操作的 IDE 功能。 例如，即使轻量级模式下只加载几个项目，也可以在整个解决方案中进行搜索。 

扩展更多项目时，Visual Studio 会记住展开项目的列表。 重新打开解决方案时，Visual Studio 会自动加载之前已展开的项目。

## <a name="visual-studio-prompts-developers-likely-to-see-significant-performance-gains"></a>Visual Studio 会提示开发人员可能会看到显著的性能提升

从 Visual Studio 遥测中，包含 30 个以上项目的大型解决方案会从 LSL 模式中显著获益。 因此，我们会提示处理大型解决方案的开发人员尝试使用 LSL 模式。 大多数开发人员第一次试用 LSL 后，最终会经常使用该模式。 

## <a name="visual-studio-makes-recommendations-to-turn-on-lightweight-solution-load-based-on-heuristics"></a>Visual Studio 基于启发，作出启用轻量级解决方案加载的建议

默认情况下，Visual Studio 会为最可能从中获益的用户启用 LSL。 如果你有多个解决方案，Visual Studio 会为最有可能显著提升性能的解决方案提供 LSL 模式。 如果选择轻量级模式选项“由 Visual Studio 决定”（默认选项），Visual Studio 可能会在基于启发的轻量级模式下打开解决方案。 消息栏会指示解决方案是否处于轻量级模式下。 消息栏显示时，可以选择了解详细信息或更新设置。

![弹出窗口](../ide/media/VSIDE_LSL_Popup.png)

## <a name="ide-features-fully-supported-in-lightweight-mode"></a>轻量级模式完全支持 IDE 功能

|功能|在轻量级模式中是否受支持？|
|-|-|-|
|IntelliSense|是|
|搜索|是|
|调试|是|
|生成|是|
|代码导航（转到定义和查找所有引用）|是|
|代码透镜|是|
|静态代码分析|是|
|部署和发布|是|
|添加和删除引用|是|
|多目标|是|
|IntelliTrace|是|
|Live Unit Testing|是|
|IntelliTest|是|
|Microsoft Fakes|是|
|编辑并继续|不支持|
|单元测试|需要在加载测试项目后进行解决方案生成|

## <a name="scenarios-in-which-lightweight-solution-loads-the-appropriate-projects-to-complete-the-operation"></a>轻量级解决方案加载相应的项目后才能完成操作的方案

如果不需要处理解决方案中的某个项目，则在轻量级模式下不会加载该项目。 对于某些功能，会自动加载其他项目，以支持功能方案。 （我们希望最小化此方案列表。 ）对于这些方案，Visual Studio 会加载项目本身，或根据需要提示你加载项目。

|类别|问题|
|-|-|-|
|单元测试|当前未加载的项目不会出现在“创建 IntelliTest”和“创建单元测试”向导的测试项目列表中。 </br>需要加载要为其创建测试的项目（可以展开项目节点来加载项目）。|
|类图|如果创建或打开项目的类图，则 Visual Studio 会自动加载作为该项目直接依赖项的项目。 </br>如果未加载整个解决方案，我们会关闭对由依赖项验证关系图引用的过时项目的验证。|

## <a name="scenarios-in-which-lightweight-solution-loads-the-entire-solution"></a>轻量级解决方案加载整个解决方案的方案 

对于某些功能，Visual Studio 会自动加载整个解决方案，以支持此方案。 此操作可确保始终获得完整的功能。 例如，某些 TFS 操作可能需要加载整个解决方案。 若要提供完整的功能，Visual Studio 会加载整个解决方案。

|类别|方案|
|-|-|-|
|解决方案节点上的 TFS SCC 命令|如果在解决方案节点上触发了 SCC 命令（在解决方案资源管理器中），Visual Studio 会在完成命令前，自动加载整个解决方案。|
|项目加载|如果解决方案包含 .NET Core 项目和共享项目，Visual Studio 会在初始解决方案加载过程中自动加载这些项目。 这些项目当前不支持轻量级模式。|
|解决方案配置管理器|如果使用解决方案配置管理器或批生成，则 Visual Studio 会自动加载整个解决方案，以提供完整的体验。|
|NuGet 程序包管理器|如果打开 NuGet 包管理器的用户界面或 NuGet 包管理器控制台，则 Visual Studio 会自动加载整个解决方案，提供完整的体验。|

## <a name="known-issues"></a>已知问题

一些方案可能无法在 LSL 模式下工作，需要加载其他项目或整个解决方案。 我们正在努力解决这些问题。 

|类别|问题|解决方法|
|-|-|-|-|
|IntelliSense|配置更改（如将发布版本更改为调试、将调试更改为发布版本）后，IntelliSense 可能没有更新。 此影响取决于配置更改导致的代码差异。|更改配置后重载解决方案。|
|重构 C# /VB 项目的限制|用于更改项目文件的代码修复第一次可能会在无提示的情况下失败。|如果需要对这些项目的文件进行代码修复，则加载项目。 轻量级模式下，无法对未加载的项目进行修复。|
|单元测试发现|手动加载项目时，在延迟项目上发现的测试不会运行。|重新生成项目，以重新发现测试并再次运行选定的测试。|
|实时单元测试 (LUT)|在 LSL 模式下，可能会看到 LUT 未激活。 未激活的原因是 LUT 需要加载其中一个测试项目。|加载任何测试项目，以激活解决方案的实时单元测试。|
|解决方案资源管理器搜索|1.  LSL 模式下的解决方案资源管理器搜索不会在文件中进行搜索，并且不存在进度结果（也就是说，在搜索树下只显示文件，而不显示类、方法等）。</br>2.  所有属于项目的文件均作为简单列表显示，而不作为树状视图显示。 文件属于项目的文件夹时，会显示该文件的相对路径，而不会只显示搜索视图上的文件名称。</br>搜索视图中没有文件项的上下文菜单。|在非 LSL 模式下加载整个解决方案，以获得传统解决方案资源管理器搜索。</br>还可以使用 Visual Studio IDE 搜索。|
|C++ 项目的对象浏览器|对象浏览器仅为已加载项目显示程序集/WinMD 引用。|加载要在对象浏览器中查看其信息的项目。|

> [!Note]
> 得益于合作伙伴的支持，Resharper 等常用扩展还适用于轻量级解决方案加载。

这些创新能够为开发人员优化解决方案加载的时间性能，我们对此感到非常高兴。 由于这是一项新的功能，我们会积极查看客户反馈，解决已知问题。 我们期待收到你的反馈。 可以通过 lslsupport@microsoft.com 向 Visual Studio 解决方案加载优化团队发送电子邮件

## <a name="see-also"></a>请参阅
[Visual Studio 性能提示和技巧](../ide/visual-studio-performance-tips-and-tricks.md)  