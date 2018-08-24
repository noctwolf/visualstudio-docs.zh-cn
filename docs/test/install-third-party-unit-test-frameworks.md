---
title: 安装第三方单元测试框架
ms.date: 06/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: ffd6b8c66f0575ec07e66ea2a138f2761b20cc7a
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379633"
---
# <a name="install-third-party-unit-test-frameworks"></a>安装第三方单元测试框架

Visual Studio 测试资源管理器可以运行任何针对该资源管理器开发了适配器接口的单元测试框架。 框架的安装程序会安装二进制文件，并为它支持的语言添加 Visual Studio 项目模板。 使用模板创建项目时，框架会向测试资源管理器注册。 Visual Studio 解决方案可以包含使用不同框架和面向不同语言的单元测试项目。 测试资源管理器可运行所有这些解决方案。

## <a name="acquire-third-party-frameworks"></a>获取第三方框架

可使用 Visual Studio Extension Manager，或从 Visual Studio Marketplace 下载并安装多种第三方单元测试框架。 还可以从其他站点（如框架的网站）下载框架。

### <a name="install-from-visual-studio"></a>通过 Visual Studio 安装

1. 在标准菜单上，依次选择“工具”和“扩展和更新”。

2. 依次展开“联机” > “Visual Studio Marketplace” > “工具”。 选择“测试”。

3. 浏览列表以查找框架。

4. 依次选择框架和“下载”。

有关详细信息，请参阅[查找和使用 Visual Studio 扩展](../ide/finding-and-using-visual-studio-extensions.md)。

### <a name="install-from-the-web"></a>从 Web 安装

如果你了解所需框架：

1. 打开 [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs)。

2. 在“查找”框中键入框架名称。

3. 在结果列表中选择框架，以导航至该工具的 Visual Studio Marketplace 页。

浏览框架以及其他测试工具的列表：

1. 打开 [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs)。

2. 在“按类别/集合筛选”中，选择“查看全部”。

3. 在“分类”列表中（标记为“显示”），展开“工具”节点，然后选择“测试”。

4. 在结果列表中选择框架，以导航到该工具的 Visual Studio Marketplace 页。

## <a name="update-to-the-latest-test-adapters"></a>更新到最新版本的测试适配器

更新到最新版本的稳定测试适配器，以体验更好的测试发现和执行。 有关更新到 MSTest、NUnit 和 xUnit 测试适配器的详细信息，请参阅 [Visual Studio 博客](https://blogs.msdn.microsoft.com/visualstudio/2017/11/16/test-experience-improvements/)。

### <a name="to-update-to-the-latest-stable-test-adapter-version"></a>更新到最新版本的稳定测试适配器

1. 导航到“工具” > “NuGet 包管理器” > “管理解决方案的 NuGet 包”，打开解决方案的 Nuget 包管理器。

2. 单击“更新”选项卡，并搜索已安装的 NUnit 或 xUnit 测试适配器。

3. 选择每个测试适配器，然后选择下拉菜单中的最新稳定版本。

4. 选择“安装”按钮。

   ![升级测试适配器](media/install-adapter-upgrade.png)

## <a name="see-also"></a>请参阅

- [单元测试代码](../test/unit-test-your-code.md)
