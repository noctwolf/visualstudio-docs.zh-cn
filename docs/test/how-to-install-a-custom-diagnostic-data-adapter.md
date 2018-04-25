---
title: 在 Visual Studio 中安装自定义诊断数据适配器 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, installing
ms.assetid: 907e65d8-0408-44b3-9e5e-e631892c1726
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 9154760fff3305343d06e63150c49db06c720ef6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-install-a-custom-diagnostic-data-adapter"></a>如何：安装自定义诊断数据适配器

如果您已创建或已具备可使用的自定义诊断数据适配器，则可通过将诊断数据适配器的程序集文件复制到本地计算机的正确目录中来安装该诊断数据适配器程序集。

 如果希望将自定义诊断数据适配器用于某个环境中的一个角色，则必须在运行可用于此角色的测试代理的所有计算机上安装该诊断数据适配器。

 下面的过程用于在适当位置安装您的自定义诊断适配器。 您将需要安装了诊断数据适配器的任何计算机上的管理权限。

## <a name="installing-a-custom-diagnostic-data-adapter"></a>安装自定义诊断数据适配器

### <a name="to-install-a-custom-diagnostic-data-adapter"></a>安装自定义诊断数据适配器

1.  若要在客户端计算机或代理计算机上运行测试时使用诊断数据适配器，请将生成目录中的所有文件复制到目标计算机上基于安装路径的以下目录中：

     %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors

     要复制的文件如下：

    -   诊断数据适配器程序集 (.dll)（必需）。

    -   适配器的调试数据文件 (.pdb)（可选）。

    -   适配器的配置文件 (`<diagnostic data adapter name>.dll.config`)，如果您有默认的配置设置的话（可选）。

    -   配置编辑器程序集，如果您已创建了一个程序集来编辑适配器的配置设置的话（可选）。 此项仅用于客户端计算机。 代理计算机不使用编辑器。

    > [!NOTE]
    > 虽然诊断数据适配器和配置编辑器可以在同一个项目中创建并且可以构建到同一个程序集中，但只要您愿意，也可以为它们使用单独的项目或创建单独的程序集。

     有关如何在运行测试时配置测试设置以使用环境的详细信息，请参阅[在手动测试中收集诊断数据 (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)。

2.  若要为测试选择诊断数据适配器，必须先选择一个现有测试设置或从 Microsoft 测试管理器或 Visual Studio 创建一个新的测试设置，然后在所选测试设置的“数据和诊断”选项卡上选择诊断数据适配器。

3.  如果已创建并安装诊断数据适配器配置编辑器，要为测试设置配置诊断数据适配器，请选择适配器旁的“配置”并进行更改。 然后选择“保存”。 有关如何为诊断数据收集器创建配置编辑器的详细信息，请参阅[如何：为诊断数据适配器创建自定义数据编辑器](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)。

4.  如果是从 Microsoft 测试管理器运行测试，则可以在运行测试前将这些测试设置分配给测试计划，也可以使用“使用选项运行”命令分配测试设置并重写测试设置。 有关测试设置的详细信息，请参阅[使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)。

     如果你是从 Visual Studio 运行测试，则必须将这些测试设置设置为处于活动状态。 有关测试设置的详细信息，请参阅[使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)。

5.  使用选择了该诊断数据适配器的测试设置运行测试。

## <a name="see-also"></a>请参阅

- [如何：创建诊断数据适配器](../test/how-to-create-a-diagnostic-data-adapter.md)
- [如何：为诊断数据适配器创建自定义数据编辑器](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [用于创建诊断数据适配器的示例项目](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [创建诊断数据适配器以收集自定义数据或影响测试计算机](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)