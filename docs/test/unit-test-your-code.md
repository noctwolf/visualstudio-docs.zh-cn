---
title: "单元测试代码 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bafabb6755a5d3c8cf8f2b60b67a9dc0d7af9792
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="unit-test-your-code"></a>单元测试代码
通过单元测试，开发人员和测试人员可以快速查找 [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)]、[!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)] 和 [!INCLUDE[cpp_current_short](../misc/includes/cpp_current_short_md.md)] 项目中各个类的方法中的逻辑错误。  
  
 单元测试工具包括：  
  
1.  **测试资源管理器。** 使用“测试资源管理器”可运行单元测试并查看结果。 “测试资源管理器”可以使用任何单元测试框架，包括具有该资源管理器的适配器的第三方框架。  
  
2.  **托管代码的 Microsoft 单元测试框架。** 托管代码的 Microsoft 单元测试框架随 Visual Studio 安装并提供测试 .NET 代码的框架。  
  
3.  **C++ 的 Microsoft 单元测试框架。** C++ 的 Microsoft 单元测试框架随 Visual Studio 安装并提供测试本机代码的框架。  Visual Studio 中还随附有 Google Test、Boost.Test 和 CTest 框架，并且提供了第三方适配器用于其他测试框架。 有关详细信息，请参阅[编写 C/C++ 单元测试](writing-unit-tests-for-c-cpp.md)。 
  
4.  **代码覆盖率工具。** 你可以确定单元测试从“测试资源管理器”中的一个命令执行的产品代码数量。  
  
5.  **Microsoft Fakes 隔离框架。** Microsoft Fakes 隔离框架可以为创建所测试代码中的依赖关系的产品和系统代码创建替代类和方法。 通过实施函数的假委托，可以控制依赖对象的行为和输出。  
  
 还可以使用 [IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md) 浏览 .NET 代码，以生成测试数据和单元测试套件。 对于代码中的每个语句，将生成执行该语句的测试输入。 为代码中的每个条件分支执行案例分析。  
  
## <a name="key-tasks"></a>关键任务  
 下面的主题可帮助你了解和创建单元测试：  
  
|任务|相关主题|  
|-----------|-----------------------|  
|**快速入门和演练：**借助以下主题从代码示例中学习 Visual Studio 中的单元测试。|-   [演练：创建并运行托管代码的单元测试](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />-   [快速入门：通过测试资源管理器进行测试驱动开发](../test/quick-start-test-driven-development-with-test-explorer.md)<br />-   [向现有的 C++ 应用程序添加单元测试](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)|  
|**使用“测试资源管理器”进行单元测试：**了解“测试资源管理器”如何帮助创建成效和效率更高的单元测试。|-   [单元测试基础](../test/unit-test-basics.md)<br />-   [创建单元测试项目](../test/create-a-unit-test-project.md)<br />-   [使用测试资源管理器运行单元测试](../test/run-unit-tests-with-test-explorer.md)<br />-   [安装第三方单元测试框架](../test/install-third-party-unit-test-frameworks.md)<br />-   [从 Visual Studio 2010 升级编码的 UI 测试](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)|  
|**对托管代码进行单元测试：**|-   [用 Microsoft 适用于托管代码的单元测试框架编写 .NET Framework 的单元测试](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)|  
|**对 C++ 代码进行单元测试**|-   [用适用于 C++ 的 Microsoft 单元测试框架编写 C/C++ 单元测试](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)|  
|**隔离单元测试**|-   [用 Microsoft Fakes 隔离测试代码](../test/isolating-code-under-test-with-microsoft-fakes.md)|  
|**使用代码覆盖率确定通过单元测试进行测试的项目代码的比例：**了解 [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] 测试工具的代码覆盖率功能。|-   [使用代码覆盖率确定所测试的代码量](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|  
|**通过对单元测试使用负载测试来执行压力和性能分析**：可以创建负载测试并向其添加单元测试，以帮助隔离应用程序中的性能和压力问题。|-   [负载测试（VSTS 和 TFS）](/vsts/load-test/)|  
|设置和强制实施质量要求：可以创建质量要求以在签入代码之前强制运行测试，从而帮助确保代码质量。|-   [设置和强制实施质量要求](http://msdn.microsoft.com/Library/bdc5666e-6cf0-45b2-a0a1-133c3f61e852)|  
|**扩展单元测试类型：**可以向可能不在单元测试框架内的测试添加功能。 例如，可以添加一个指定某个测试是否应以普通用户身份运行的测试属性。 也可以扩展框架，将行特性添加到某个方法并在测试内使用该行中的数据。|有关如何扩展单元测试框架的示例代码，请参见以下 [Microsoft 网站](http://go.microsoft.com/fwlink/?LinkId=185591)。|  
|**设置测试选项：**例如，可以指定测试结果的存储位置。|[使用 .runsettings 文件配置单元测试](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|  
  
## <a name="reference"></a>参考  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>  
 介绍 UnitTesting 命名空间，该命名空间提供支持单元测试的特性、异常、断言和其他类。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web>  
 介绍 UnitTesting.Web 命名空间，该命名空间通过提供对 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 和 Web 服务单元测试的支持扩展了 UnitTesting 命名空间。  
  
## <a name="external-resources"></a>外部资源  
  
### <a name="videos"></a>视频  
 [Channel 9: Unit testing your UWP apps built using XAML](http://go.microsoft.com/fwlink/?LinkId=226285)（第 9 频道：对使用 XAML 生成的 UWP 应用进行单元测试）  
  
### <a name="forums"></a>论坛  
 [Visual Studio 单元测试](http://go.microsoft.com/fwlink/?LinkId=224477)  
  
### <a name="guidance"></a>指导  
 [使用 Visual Studio 2012 测试连续交付 - 第 2 章：单元测试：测试内部](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
### <a name="reference"></a>参考  
 [Content Index for Unit Tests](http://go.microsoft.com/fwlink/?LinkID=254719)（单元测试的内容索引）  
  
## <a name="see-also"></a>请参阅

[提高代码质量](/visualstudio/test/improve-code-quality)
