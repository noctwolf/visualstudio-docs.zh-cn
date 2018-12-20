---
title: 单元测试入门
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit test plans
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6e8835edb2b340778c4431d3de5b554d6aeb6c6d
ms.sourcegitcommit: 0cdd8e8a53fb4fd5e869f07c35204419fa12783d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53158809"
---
# <a name="get-started-with-unit-testing"></a>单元测试入门

使用 Visual Studio 定义和运行单元测试，使代码保持正常运行、确保代码覆盖率并在客户之前找到错误和缺陷。

## <a name="create-unit-tests"></a>创建单元测试

创建单元测试并经常运行，确保代码正常运行。

1. 创建单元测试项目。

   ![向解决方案添加单元测试项目](media/createunittest1.png)

1. 为项目命名。

   ![单元测试项目模板](media/createunittest2.png)

   项目将添加到解决方案中。

   ![解决方案资源管理器中的单元测试项目](media/createunittest5.png)

1. 在单元测试项目中，向要测试的项目中添加一个引用。

   ![向单元测试项目添加引用](media/createunittest6.png)

1. 选择包含待测试代码的项目。

   ![选择要添加的引用](media/createunittest7.png)

1. 对单元测试进行编码。

   ![将代码添加到单元测试](media/createunittest8.png)

可使用“创建单元测试”[命令](create-unit-tests-menu.md)创建单元测试方法存根。

![使用“创建单元测试”命令](media/createunittestcommand2.png)

## <a name="run-unit-tests"></a>运行单元测试

1. 打开“测试资源管理器”。

   ![在“测试”菜单上，打开“测试资源管理器”](media/rununittest1.png)

1. 运行单元测试。

   ![在测试资源管理器中运行单元测试](media/rununittest2.png)

   在“测试资源管理器”中，可看到通过或未通过的单元测试。

   ![在测试资源管理器中查看单元测试结果](media/rununittest3.png)

## <a name="view-live-unit-test-results"></a>查看实时单元测试结果

如果在 Visual Studio 2017 或更高版本中使用 MSTest、xUnit 或 NUnit 测试框架，可查看单元测试的实时结果。

> [!NOTE]
> 只有 Visual Studio 2017 Enterprise Edition 中提供实时单元测试。

1. 从“测试”菜单启用 Live Unit Testing。

   ![启用 Live Unit Testing](media/live-test-results-start.png)

1. 编写和编辑代码时，请在代码编辑器窗口中查看测试的结果。

   ![查看测试的结果](media/live-test-results-ui.png)

1. 选择测试结果指示符以查看详细信息。

   ![选择测试结果指示符](media/live-test-results-details.png)

有关详细信息，请参阅 [Live unit testing](../test/live-unit-testing-intro.md)。

## <a name="generate-unit-tests-with-intellitest"></a>使用 IntelliTest 生成单元测试

当你运行 IntelliTest 时，你可轻松看到哪些测试会失败，并可添加任何必要的代码来修复它们。 你可选择要保存到测试项目中的已生成测试，以提供回归套件。 当你更改代码时，重新运行 IntelliTest，以使生成的测试与你的代码更改同步。 若要了解如何操作，请参阅[使用 IntelliTest 为你的代码生成单元测试](../test/generate-unit-tests-for-your-code-with-intellitest.md)。

![使用 IntelliTest 生成单元测试](media/intellitest.png)

## <a name="run-unit-tests-with-test-explorer"></a>使用测试资源管理器运行单元测试

使用“测试资源管理器”从 Visual Studio 或第三方单元测试项目中运行单元测试、将测试分组到类别中、筛选测试列表以及创建、保存和运行测试的播放列表。 你还可以调试测试并分析测试性能和代码覆盖率。 若要了解如何操作，请参阅[使用测试资源管理器运行单元测试](../test/run-unit-tests-with-test-explorer.md)。

![使用测试资源管理器运行单元测试](media/testexplorer.png)

## <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>使用代码覆盖率确定所测试的代码量

若要确定正在由编码的测试（例如单元测试）实际进行测试的项目代码的比例，则可以使用 Visual Studio 的代码覆盖率功能。 若要有效防止 Bug，测试应作用于你的大部分代码。 若要了解如何操作，请参阅[使用代码覆盖率确定所测试的代码量](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)。

## <a name="use-a-different-unit-test-framework"></a>使用不同的单元测试框架

通过使用第三方测试框架（如 Boost、Google、和 NUnit），可以在 Visual Studio 中运行单元测试。 采用针对该框架的插件，以便 Visual Studio 测试运行程序能够使用该框架。

下面是启用第三方测试框架的操作步骤：

1. 从菜单栏选择“工具” > “扩展和更新”。

1. 在“扩展和更新”对话框中，展开“联机”类别，然后选择“Visual Studio Marketplace”。 然后选择“工具” > “测试”。

   ![Visual Studio Marketplace](media/extensions-and-updates-testing.png)

1. 选择想要安装的框架或适配器，然后选择“下载”。

1. 创建一个类库项目，并将其添加到解决方案中。

   ![命名类库项目命名并添加它](media/create3rdpartyunittest3.png)

1. 安装插件。 在“解决方案资源管理器”中，选择类库项目，然后通过右键单击或从上下文菜单中选择“管理 NuGet 包”。

   ![管理 NuGet 程序包以安装插件](media/create3rdpartyunittest3a.png)

   [NuGet](https://www.nuget.org/) 是 Visual Studio 的扩展，可用来添加和更新项目使用的库和工具。

1. 在“NuGet 包管理器”窗口中，搜索和选择插件，然后选择“安装”。

   ![安装第三方框架](media/create3rdpartyunittest4.png)

   框架在项目中得到引用。

   ![将第三方单元测试框架的引用添加到解决方案中](media/create3rdpartyunittest6.png)

1. 从类库项目的“引用”节点，选择“添加引用”。

   ![添加对项目的引用](media/createunittest6.png)

1. 在“引用管理器”对话框中，选择包含待测试代码的项目。

   ![选择要测试的代码项目](media/createunittest7.png)

1. 对单元测试进行编码。

   ![将代码添加到单元测试代码文件](media/create3rdpartyunittest7.png)

## <a name="see-also"></a>请参阅

* [创建单元测试命令](create-unit-tests-menu.md)
* [使用 IntelliTest 生成测试](generate-unit-tests-for-your-code-with-intellitest.md)
* [使用测试资源管理器运行测试](run-unit-tests-with-test-explorer.md)
* [确定代码覆盖率](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [提高代码质量](improve-code-quality.md)