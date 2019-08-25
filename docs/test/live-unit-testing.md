---
title: Live Unit Testing
ms.date: 03/07/2017
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: bfe1affaad05d2c20a27fb0e315fc1d3b263f22b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923753"
---
# <a name="live-unit-testing-with-visual-studio"></a>使用 Visual Studio 执行 Live Unit Testing

在你开发应用程序时，Live Unit Testing 将在后台自动运行任何受影响的单元测试并在 Visual Studio IDE 中实时显示结果和代码覆盖率。 在你修改代码时，Live Unit Testing 可提供关于更改如何影响现有测试和新增代码是否会被一个或多个现存测试覆盖的反馈。 这可在你进行 bug 修复或添加新功能时，温馨地提示你编写单元测试。

> [!NOTE]
> Live Unit Testing 适用于面向 Visual Studio Enterprise Edition 中的 .NET Core 或 .NET Framework 的 C# 和 Visual Basic 项目。

使用 Live Unit Testing 进行测试时，Live Unit Testing 会保留测试状态数据。 由于可以使用持久化数据，因此 Live Unit Testing 的性能更优异，同时还能动态运行测试，以响应代码变化。

## <a name="supported-test-frameworks"></a>受支持的测试框架
Live Unit Testing 适用于下表中列出的三个常用的单元测试框架。 表中还列出了其适配器和框架支持的最低版本。 单元测试框架都可从 NuGet.org 获得。

|测试框架  |Visual Studio 适配器最低版本  |Framework 最低版本  |
|---------|---------|---------|
|xUnit.net |xunit.runner.visualstudio 版本 2.2.0-beta3-build1187 |xunit 1.9.2 |
|NUnit |NUnit3TestAdapter 版本 3.5.1 |NUnit 版本 3.5.0 |
|MSTest |MSTest.TestAdapter 1.1.4-预览版 |MSTest.TestFramework 1.0.5-预览版 |

如果你有正在引用 `Microsoft.VisualStudio.QualityTools.UnitTestFramework` 的测试项目（该项目是基于较旧的 MSTest），并且不想移动到较新的 MSTest NuGet 包，请升级到 Visual Studio 2017 版本 15.4 或更高版本。

在某些情况下，可能需要显式还原解决方案中项目引用的 NuGet 包，以便 Live Unit Testing 可正常运行。 可先通过显式生成解决方案（从顶级 Visual Studio 菜单中选择“生成” > “重新生成解决方案”）或通过还原解决方案中的包（右键单击解决方案并选择“还原 NuGet 包”）实现此操作，然后再启用 Living Unit Testing    。

## <a name="configure-live-unit-testing"></a>配置 Live Unit Testing

可按以下方式配置 Live Unit Testing：从顶级 Visual Studio 菜单栏中选择“工具” > “选项”，然后在“选项”对话框左窗格中选择“Live Unit Testing”     。

> [!TIP]
> 启用 Live Unit Testing 后（详见[启动、暂停和停止 Live Unit Testing](#start-pause-and-stop-live-unit-testing) 部分），还可通过选择“测试” > “Live Unit Testing” > “选项”打开“选项”对话框     。

下图显示对话框中可用的 Live Unit Testing 配置选项：

  ![图像](./media/lut-options.png)

可配置选项包括：

- 是否在生成和调试解决方案时暂停 Live Unit Testing。

- 是否在系统电量低于指定阈值时暂停 Live Unit Testing。

- 打开解决方案时 Live Unit Testing 是否自动运行。

- 是否启用调试符号和 XML 文档注释生成。

- 持久化数据存储目录。

- 删除所有持久化数据的功能。 当 Live Unit Testing 的行为不可预测或出现异常时（表明持久化数据已损坏），这就很有用。

- 测试用例超时之前的时间间隔；隔默认值为 30 秒。

- Live Unit Testing 可创建的测试进程数上限。

- Live Unit Testing 进程可占用的内存上限。

- 写入 Live Unit Testing“输出”  窗口的信息级别。

   选项包括无日志记录（“无”  ）、仅限错误消息（“错误”  ）、错误和信息性消息（默认值为“信息”  ）或所有详细信息（“详细”  ）。

   还可向名为 `VS_UTE_DIAGNOSTICS` 的用户级环境变量分配值“1”，再重启 Visual Studio，从而在 Live Unit Testing 的“输出”窗口显示详细输出  。

   要捕获文件中 Live Unit Testing 的详细 MSBuild 日志消息，请将 `LiveUnitTesting_BuildLog` 用户级环境变量设为该文件的名称以包含日志。

## <a name="start-pause-and-stop-live-unit-testing"></a>启动、暂停和停止 Live Unit Testing

通过从顶级 Visual Studio 菜单中依次选择“测试” > “Live Unit Testing” > “启动”来启用 Live Unit Testing    。 启用 Live Unit Testing 后，“Live Unit Testing”  菜单上的可用选项从一个“开始”  项变为“暂停”  、“停止”  和“重置清理”  。

> [!NOTE]
> 如果在不包含单元测试项目的解决方案中启动 Live Unit Testing，“Live Unit Testing”菜单上会显示“暂停”、“停止”和“重置清理”选项，但 Live Unit Testing 不会启动     。 “输出”窗口显示以“此解决方案没有引用受支持的测试适配器...”开头的消息 

在任何时候，都可以临时暂停或完全停止 Live Unit Testing。 例如，当你正在重构且知道测试将停止一段时间时，你可能想要执行此操作。 三个菜单选项为：

- **暂停**，用于临时挂起 Live Unit Testing。

    暂停 Live Unit Testing 后，覆盖率可视化效果不会出现在编辑器中，但会保留所有已收集的数据。 若要恢复 Live Unit Testing，请选择”Live Unit Testing”菜单中的“继续”  。 Live Unit Testing 将执行必要工作，以便与其暂停时所做的全部编辑保持同步，并相应地更新字形。

- **停止**，用于完全停止 Live Unit Testing。 Live Unit Testing 将放弃已收集的所有数据。

- **重置清理**：可停止 Live Unit Testing、删除持久化数据，并重启 Live Unit Testing。

- **选项**：可打开[配置 Live Unit Testing](#configure-live-unit-testing) 部分中所述的“选项”对话框  。

## <a name="view-coverage-visualization-in-the-editor-as-you-type"></a>在编辑器中查看键入时的覆盖率可视化效果

一旦启用，Live Unit Testing 将在 Visual Studio 编辑器中更新每行代码，以显示正在编写的代码是否由单元测试覆盖以及覆盖这些代码的测试是否通过。  下图显示测试通过和失败的代码行，以及测试未覆盖的代码行。 绿色“✓”修饰的行只表示通过测试，红色“x”修饰的行表示未通过一项或多项测试，蓝色“➖”修饰的行表示未经过任何测试。

  ![图像](./media/lut-codewindow.png)

当你在代码编辑器中修改代码后，将立即更新 Live Unit Testing 覆盖率可视化效果。 处理编辑时，可视化效果将变化，通过在通过、失败和未覆盖符号下方添加圆形计时器图像来指示数据非最新，如下图所示。

  ![图像](./media/lut-codeupdating.png)

## <a name="get-information-on-successful-or-failed-tests"></a>获取关于成功或失败测试的信息

将鼠标悬停在代码窗口中的成功或失败符号上，可以看到符合此条件的测试数目。 如果单击符号，可以查看各个测试的状态，如下图所示：

  ![图像](./media/lut-failedinfo.png)

除了提供测试名称和结果之外，工具提示还支持重新运行测试集，并使用调试程序运行测试集。 如果选择工具提示中的一个或多个测试，还可以仅运行或调试这些测试。 这样，不用离开代码窗口，就可以调试测试。 调试时，除了遵循已设置的所有断点外，程序执行还会在调试器执行返回意外结果的 [`Assert`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert) 方法时暂停。

如果将鼠标悬停于工具提示中的未通过测试之上，测试将展开，以提供未通过测试详细信息，如下图所示。 如果双击工具提示中的未通过测试，可以直接转到它。

  ![图像](./media/lut-failedmsg.png)

转到未通过测试时，Live Unit Testing 也会在方法签名中直观地指出已通过测试（标有半满烧杯和绿色的“✓”）、未通过测试（标有半满烧杯和红色的“🞩”）或 Live Unit Testing 未涉及测试（标有半满烧杯和蓝色的“➖”）。 非测试方法使用符号进行修饰。 下图展示了所有四种类型的方法。

  ![图像](media/lut-testsource.png)

## <a name="diagnose-and-correct-test-failures"></a>诊断和更正测试失败

根据失败测试，你可以轻松对产品代码进行调试、进行编辑，并继续开发应用程序。 由于 Live Unit Testing 在后台运行，因此无需在调试、编辑和继续循环期间停止和重启 Live Unit Testing。

例如，上图中的测试未通过原因是，在测试方法中错误地认为非字母字符在传递到 <xref:System.Char.IsLower%2A?displayProperty=fullName> 方法时返回 `true`。 更正测试方法后，我们发现所有测试均通过。 我们执行此操作时，不需要暂停或停止 Live Unit Testing。

## <a name="live-unit-testing-and-test-explorer"></a>Live Unit Testing 和测试资源管理器

通常，**测试资源管理器**具有可供运行、调试和分析测试结果的界面。 Live Unit Testing 与**测试资源管理器**集成。 当 Live Unit Testing 未启用或已停止时，**测试资源管理器**将显示上次运行测试时的单元测试状态。 源代码更改需要重新运行测试。 与此相反，启用 Live Unit Testing 后，**测试资源管理器**中的单元测试状态将立即更新。 不再需要显式运行单元测试。

> [!NOTE]
> 可在顶级 Visual Studio 菜单中依次选择“测试” > “Windows” > “测试资源管理器”，打开测试资源管理器     。

可能会注意到，在“测试资源管理器”  窗口中，一些测试已淡化。例如，如果在打开以前保存的项目后启用 Live Unit Testing，除了未通过测试外，“测试资源管理器”  窗口淡化了所有测试，如下图所示。 在此示例中，Live Unit Testing 已重新运行未通过测试，但没有重新运行已通过测试，因为 Live Unit Testing 的持久化数据表明，自上一次成功运行测试以来没有任何变化。

  ![图像](media/lut-test-explorer.png)

可以重新运行淡化的任何测试，具体方法是选择“测试资源管理器”  菜单上的“全部运行”  或“运行”  选项，或选择并右键单击“测试资源管理器”  菜单中的一个或多个测试，再从弹出菜单中选择“运行选定测试”  或“调试选定测试”  。 运行的测试会向上冒到顶部。

Live Unit Testing 自动运行、更新测试结果与通过“测试资源管理器”  显式运行测试结果有所不同。 区别包括：

- 从测试资源管理器窗口运行或调试测试将运行常规二进制文件，而 Live Unit Testing 运行已检测二进制文件。
- Live Unit Testing 不会新建应用程序域来运行测试，而是通过默认域运行测试。 从**测试资源管理器**窗口运行的测试确实会创建新的应用程序域。
- Live Unit Testing 按顺序运行每个测试程序集中的测试。 在“测试资源管理器”窗口中，可以选择一个选项以并行运行多个测试  。

## <a name="live-unit-testing-and-large-solutions"></a>Live Unit Testing 和大型解决方案

如果解决方案包含 10 个或更多项目，那么当用户启动 Live Unit Testing 且没有永久性数据时，或当用户在顶级 Visual Studio 菜单中依次选择“测试” > “Live Unit Testing” > “重置清理”选项时，Visual Studio 会显示下面的对话框，以警告用户在大型项目中动态运行大量测试可能会严重影响性能    。 如果用户选择“确定”  ，Live Unit Testing 会在解决方案中执行所有测试。 如果用户选择“取消”  ，可以选择要执行的测试。 有关如何执行此操作的信息，请参阅以下部分：[包括和排除测试项目和测试方法](#include-and-exclude-test-projects-and-test-methods)。

![大型项目的“Live Unit Testing”对话框](media/lut-large-project.png)

## <a name="include-and-exclude-test-projects-and-test-methods"></a>包括和排除测试项目和测试方法

对于含多个测试项目的解决方案，可以控制参与 Live Unit Testing 的项目和项目中的单个方法。 例如，如果解决方案包含数百个测试项目，可以选择一组目标测试项目，以参与 Live Unit Testing。 这样做的方法有很多，具体取决于是要排除项目或解决方案中的所有测试、包括或排除大部分测试，还是要排除个别测试。 关闭或重新打开解决方案时，Live Unit Testing 将包括/排除状态另存为用户设置并将其记住。

**排除项目或解决方案中的所有测试**

若要在单元测试中选择单个项目，请在启动 Live Unit Testing 后执行以下操作：

1. 在解决方案资源管理器中右键单击解决方案并依次选择“Live Unit Testing” > “排除”以排除整个解决方案    。
1. 右键单击想要包括在测试中的每个测试项目，然后依次选择“Live Unit Testing” > “包括”   。

**从代码编辑器窗口中排除个别测试**

可以使用代码编辑器窗口，包括或排除个别测试方法。 右键单击代码编辑器窗口中测试方法的签名，再选择“Live Unit Testing” > “包括 [选定方法]”、“Live Unit Testing” > “排除 [Live Unit Testing]”或“实时测试” > “排除 [选定方法] 以外的所有方法”，其中“选定方法”是在代码窗口中已选的方法名称       。

**以编程方式排除测试**

可以应用 <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> 属性，以编程方式排除方法、类或结构，将其从 Live Unit Testing 中的覆盖率报表剔除。

还可以使用以下属性，从 Live Unit Testing 中排除个别方法：

- 对于 xUnit：`[Trait("Category", "SkipWhenLiveUnitTesting")]`
- 对于 NUnit：`[Category("SkipWhenLiveUnitTesting")]`
- 对于 MSTest：`[TestCategory("SkipWhenLiveUnitTesting")]`

## <a name="see-also"></a>请参阅

- [代码测试工具](https://visualstudio.microsoft.com/vs/testing-tools/)
- [Live Unit Testing 博客](https://go.microsoft.com/fwlink/?linkid=842514)
- [实时单元测试常见问题解答](live-unit-testing-faq.md)
- [第 9 频道视频：Visual Studio 中的 Live Unit Testing](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T105)
