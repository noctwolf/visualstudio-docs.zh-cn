---
title: Visual Studio 测试资源管理器常见问题解答 | Microsoft Docs
ms.date: 1/15/2018
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
ms.openlocfilehash: 7612f13f71bed42b5ea416a74c50674ac028f42f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="visual-studio-test-explorer-faq"></a>Visual Studio 测试资源管理器常见问题解答

## <a name="test-discovery"></a>测试发现

### <a name="1-the-test-explorer-is-not-discovering-my-tests-that-are-dynamically-defined-for-example-theories-custom-adapters-custom-traits-ifdefs-etc-how-can-i-discover-these-tests"></a>1.测试资源管理器未发现动态定义的测试。 （例如，理论、自定义适配器、自定义特征和 #ifdef 等）如何发现这些测试？

  请生成您的项目，并确保在“工具 > 选项 > 测试”中打开基于程序集的发现。

  [实时测试发现](https://go.microsoft.com/fwlink/?linkid=862824)是一种基于源的测试发现功能。 该功能无法发现使用理论、自定义适配器、自定义特性和 `#ifdef` 语句等的测试，因为这些项是在运行时定义的。 此类测试需要在生成后才能被准确发现。 在 15.6 预览版中，基于程序集的发现（传统发现）仅在生成后运行。 此设置表示“实时测试发现”可在你编辑时发现尽可能多的测试，而通过基于程序集的发现，可在生成后显示自动定义的测试。 “实时测试发现”改进了响应能力，但仍可让你在生成后获取完整且准确的结果。

### <a name="2-what-does-the--plus-symbol-that-appears-in-the-top-line-of-test-explorer-mean"></a>2.测试资源管理器首行中出现的加号 (+) 是什么意思？

  加号 (+) 表示，只要启用基于程序集的发现，即可在生成后发现更多测试。 如果在项目中检测到动态定义的测试，也会出现加号。

  ![加号汇总行](media/testex-plussymbol.png)

### <a name="3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on"></a>3.基于程序集的发现不再对我的项目有效。 如何重新启动它？

  请转到“工具”>“选项”>“测试”，选中“还在生成后从已生成的程序集中发现测试”框。

  ![基于程序集的选项](media/testex-toolsoptions.png)

### <a name="4-tests-now-appear-in-test-explorer-while-i-type-without-having-to-build-my-project-what-changed"></a>4.在我键入时，测试现在会显示在测试资源管理器中，而不必生成我的项目。 进行了哪些更改？

  此功能被称为[实时测试发现](https://go.microsoft.com/fwlink/?linkid=862824)。 它使用 Roslyn 分析器来发现测试并实时填充测试资源管理器，而无需你生成项目。 若要深入了解动态定义测试（如理论或自定义特征）的测试发现行为，请参阅常见问题解答 1。

### <a name="5-what-languages-and-test-frameworks-can-use-real-time-test-discovery"></a>5.哪些语言和测试框架可以使用实时测试发现？

  由于是使用 Roslyn 编译器生成的[实施测试发现](https://go.microsoft.com/fwlink/?linkid=862824)，因此，其仅适用于托管语言（C# 和 Visual Basic）。 目前，实时测试发现仅适用于 xUnit、NUnit 和 MSTest 框架。

### <a name="6-how-can-i-turn-on-logs-for-the-test-explorer"></a>6.如何针对测试资源管理器打开日志？

  导航到“工具”>“选项”>“测试”，并在此处找到“日志记录”部分。

### <a name="7-why-are-my-tests-in-uwp-projects-not-discovered-until-i-deploy-my-app"></a>7.为何在我部署应用之前，系统未发现 UWP 项目中的测试？

  UWP 测试面向的是部署应用时的另一个运行时。 这表示，你需要构建项目，还需要进行部署，才能正确地发现用于 UWP 项目的测试。

### <a name="8-how-does-sorting-test-results-work-in-the-hierarchy-view"></a>8.如何在层次结构视图中进行测试结果排序？

  层次结构视图按字母顺序对测试进行排序（与按结果排序相反）。 按设置划分的另一组通常按结果对测试结果进行排序，然后按字母排序。 在下图中根据选项查看不同组以进行比较。 可通过[此 GitHub 问题](https://github.com/Microsoft/vstest/issues/1425)提供设计方面的反馈。

  ![SortingExamples](media/testex-sortingex.png)

### <a name="9-in-the-hierarchy-view-there-are-passed-failed-skipped-and-not-run-icons-next-to-the-project-namespace-and-class-groupings-what-do-these-icons-mean"></a>9.在层次结构视图中，“项目”、“命名空间”和“类”分组旁存在“已传递”、“失败”、“已跳过”和“不运行”图标。 这些图标代表什么？

  “项目”、“命名空间”和“类”分组旁的图标反映该分组中的测试状态。 请参见下表。

  ![测试资源管理器层次结构图标](media/testex-hierarchyicons.png)
  
### <a name="10-there-is-no-longer-a-file-path-filter-in-the-test-explorer-search-box"></a>10.测试资源管理器搜索框中不再有“文件路径”筛选器。

Visual Studio 2017 版本 15.7 预览版 3 已删除“测试资源管理器”搜索框中的文件路径筛选器。 此功能的使用率较低，测试资源管理器删除此功能后可提升测试方法的检索速度。 如果此更改会中断你的开发流，请通过[开发人员社区](https://developercommunity.visualstudio.com/)向我们提供反馈。

## <a name="features"></a>功能

### <a name="how-can-i-turn-on-feature-flags-to-try-out-new-testing-features"></a>如何打开功能标志来试用新的测试功能？

功能标志用于发布试验版或产品的未完成部分，以便在功能正式发布让热心用户给予反馈。 它们可能会破坏 IDE 体验的稳定性。 仅在虚拟机等安全开发环境中使用。 功能标志始终是风险自负的设置。 你可以使用[功能标志扩展](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension)或通过开发人员命令提示符开启试验功能。

![功能标志扩展](media/testex-featureflag.png)

若要通过 Visual Studio 开发人员命令提示开启功能标志，请使用以下命令。 将路径更改为 Visual Studio 在计算机上的安装位置并且将注册表项更改为所需功能标志。

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise” HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> 通过在 dword 后使用值 0 而不是 1 可使用相同命令关闭标志。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>
- [为现有代码创建和运行单元测试](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
- [单元测试代码](unit-test-your-code.md)
- [实时单元测试常见问题解答](live-unit-testing-faq.md)
