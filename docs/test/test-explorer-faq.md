---
title: Visual Studio 测试资源管理器常见问题解答
ms.date: 1/15/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Test Explorer
- Test window
- Visual Studio Test Explorer
- summary line
- unit tests
- Test Explorer FAQ
ms.author: kehavens
ms.workload:
- multiple
author: kendrahavens
manager: douge
ms.openlocfilehash: 069150d7f441b754b21c0a3a487f5238ef94e039
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43775099"
---
# <a name="visual-studio-test-explorer-faq"></a>Visual Studio 测试资源管理器常见问题解答

## <a name="dynamic-test-discovery"></a>动态测试发现
测试资源管理器未发现动态定义的测试。（例如，理论、自定义适配器、自定义特征和 #ifdef 等）如何发现这些测试？

  请生成项目，并确保在“工具” > “选项” > “测试”中打开基于程序集的发现。

  [实时测试发现](https://go.microsoft.com/fwlink/?linkid=862824)是一种基于源的测试发现功能。 该功能无法发现使用理论、自定义适配器、自定义特性和 `#ifdef` 语句等的测试，因为这些项是在运行时定义的。 此类测试需要在生成后才能被准确发现。 在 Visual Studio 2017 版本 15.6 及更高版本中，基于程序集的发现（传统发现）仅在生成后运行。 此设置表示“实时测试发现”可在你编辑时发现尽可能多的测试，而通过基于程序集的发现，可在生成后显示自动定义的测试。 “实时测试发现”改进了响应能力，但仍可让你在生成后获取完整且准确的结果。

## <a name="test-explorer--plus-symbol"></a>测试资源管理器加号 (+)
测试资源管理器首行中出现的加号 (+) 是什么意思？

  加号 (+) 表示，只要启用基于程序集的发现，即可在生成后发现更多测试。 如果在项目中检测到动态定义的测试，也会出现加号。

  ![加号汇总行](media/testex-plussymbol.png)

## <a name="assembly-based-discovery"></a>基于程序集的发现
基于程序集的发现不再对我的项目有效。如何重新启动它？

  请转到“工具” > “选项” > “测试”，选中“另外，生成后从已生成的程序集中发现测试”框。

  ![基于程序集的选项](media/testex-toolsoptions.png)

## <a name="real-time-test-discovery"></a>实时测试发现
在我键入时，测试现在会显示在测试资源管理器中，而不必生成我的项目。进行了哪些更改？

  此功能称为[实时测试发现](https://go.microsoft.com/fwlink/?linkid=862824)。 它使用 Roslyn 分析器来发现测试并实时填充测试资源管理器，而无需你生成项目。 若要深入了解动态定义测试（如理论或自定义特征）的测试发现行为，请参阅常见问题解答 1。

## <a name="real-time-test-discovery-compatibility"></a>实时测试发现兼容性
哪些语言和测试框架可以使用实时测试发现？

  由于[实施测试发现](https://go.microsoft.com/fwlink/?linkid=862824)是使用 Roslyn 编译器生成的，因此仅适用于托管语言（C# 和 Visual Basic）。 目前，实时测试发现仅适用于 xUnit、NUnit 和 MSTest 框架。

## <a name="test-explorer-logs"></a>测试资源管理器日志
如何针对测试资源管理器打开日志？

  导航到“工具” > “选项” > “测试”，并在此处找到“日志记录”部分。

## <a name="uwp-test-discovery"></a>UWP 测试发现
为何在我部署应用之前，系统未发现 UWP 项目中的测试？

  UWP 测试面向的是部署应用时的另一个运行时。 这表示，你需要构建项目，还需要进行部署，才能正确地发现用于 UWP 项目的测试。

## <a name="test-explorer-sorting"></a>测试资源管理器排序
如何在层次结构视图中进行测试结果排序？

  层次结构视图按字母顺序对测试进行排序（与按结果排序相反）。 按设置划分的另一组通常按结果对测试结果进行排序，然后按字母排序。 在下图中根据选项查看不同组以进行比较。 可通过[此 GitHub 问题](https://github.com/Microsoft/vstest/issues/1425)提供设计方面的反馈。

  ![SortingExamples](media/testex-sortingex.png)

## <a name="test-explorer-hierarchy-view"></a>测试资源管理器层次结构视图
在层次结构视图中，“项目”、“命名空间”和“类”分组旁存在“已传递”、“失败”、“已跳过”和“不运行”图标。这些图标代表什么？

  “项目”、“命名空间”和“类”分组旁的图标反映该分组中的测试状态。 请参见下表。

  ![测试资源管理器层次结构图标](media/testex-hierarchyicons.png)

## <a name="search-by-file-path"></a>按文件路径搜索
测试资源管理器搜索框中不再有“文件路径”筛选器。

Visual Studio 2017 版本 15.7 预览版 3 已删除“测试资源管理器”搜索框中的文件路径筛选器。 此功能的使用率较低，测试资源管理器删除此功能后可提升测试方法的检索速度。 如果此更改会中断你的开发流，请通过[开发人员社区](https://developercommunity.visualstudio.com/)向我们提供反馈。

## <a name="test-adapter-nuget-reference"></a>测试适配器 NuGet 引用
在 Visual Studio 2017 版本 15.8 中，发现了我的测试但不执行。

所有测试项目必须在其 csproj 中包含各自的 .NET 测试适配器 NuGet 引用。 如果未包含，在生成之后启动测试适配器扩展的发现或用户尝试运行所选测试时，项目中将显示以下测试输出： 

测试项目 {} 不引用任何 .NET NuGet 适配器。测试发现或执行可能不适用于此项目。建议在解决方案的每个 .NET 测试项目中引用 NuGet 测试适配器。

项目需要使用测试适配器 NuGet 包，而不使用测试适配器扩展。 这极大地提高了性能，并通过持续集成减少产生的问题。 阅读[发行说明](/visualstudio/releasenotes/vs2017-preview-relnotes#testadapterextension)中有关 .NET 测试适配器扩展弃用的详细信息。

> [!NOTE]
> 如果使用 NUnit 2 测试适配器且无法迁移到 NUnit 3 测试适配器，则可以在 Visual Studio 15.8 版的“工具” > “选项” > “测试”中关闭这一新发现行为。 

  ![“工具”选项中的测试资源管理器适配器行为](media/testex-adapterbehavior.png)

## <a name="uwp-testcontainer-was-not-found"></a>未找到 UWP TestContainer
我的 UWP 测试不再在 Visual Studio 2017 版本 15.7 及更高版本中执行。

最近的 UWP 测试项目指定了一个测试平台生成属性，通过它可提供更佳的测试应用识别性能。 如果具有在 Visual Studio 版本 15.7 之前初始化的 UWP 测试项目，可能会在“输出” > “测试”中看到以下错误：

System.AggregateException: 发生一个或多个错误。---> System.InvalidOperationException: 在 {}Microsoft.VisualStudio.TestWindow.Controller.TestContainerProvider <GetTestContainerAsync>d__61.MoveNext() 中找不到以下 TestContainer
  
修复此问题的方法：
- 将测试项目生成属性更新为以下内容：

```XML
<UnitTestPlatformVersion Condition="'$(UnitTestPlatformVersion)' == ''">$(VisualStudioVersion)</UnitTestPlatformVersion>
```

- 将 TestPlatform SDK 版本更新为以下内容：

```XML
<SDKReference Include="TestPlatform.Universal, Version=$(UnitTestPlatformVersion)" />
```

## <a name="using-feature-flags"></a>使用功能标志
如何打开功能标志来试用新的测试功能？

功能标志用于发布试验版或产品的未完成部分，以便在功能正式发布让热心用户给予反馈。 它们可能会破坏 IDE 体验的稳定性。 仅在虚拟机等安全开发环境中使用。 功能标志始终是风险自负的设置。 可使用[功能标志扩展](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension)或通过开发人员命令提示符开启试验功能。

![功能标志扩展](media/testex-featureflag.png)

若要通过 Visual Studio 开发人员命令提示开启功能标志，请使用以下命令。 将路径更改为 Visual Studio 在计算机上的安装位置并且将注册表项更改为所需功能标志。

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise" HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> 通过在 dword 后使用值 0 而不是 1 可使用相同命令关闭标志。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>
- [创建并运行现有代码的单元测试](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
- [单元测试代码](unit-test-your-code.md)
- [Live Unit Testing 常见问题解答](live-unit-testing-faq.md)
