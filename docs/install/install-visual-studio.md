---
title: 安装 Visual Studio
titleSuffix: ''
description: 了解如何逐步安装 Visual Studio。
ms.date: 05/07/2018
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- vs.about
helpviewer_keywords:
- install Visual Studio
- dev15
- set up Visual Studio
- Visual Studio setup
- Visual Studio installer
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fab4a79bfd7a72b6b81493db241cd1ade8068158
ms.sourcegitcommit: 34940a18f5b03a59567f54c7024a0b16d4272f1e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56156132"
---
# <a name="install-visual-studio-2017"></a>安装 Visual Studio 2017

欢迎以全新方式安装 Visual Studio！ 最新版本方便你更轻松地选择并仅安装所需功能。 此外，我们还减少了 Visual Studio 的最小内存需求量，使其安装速度变得更快，对系统的影响更小。

> [!NOTE]
> 本主题适用于 Visual Studio  Windows 版。 对于 Visual Studio for Mac，请参阅[安装 Visual Studio for Mac](/visualstudio/mac/installation)。

想要详细了解此版本的其他新增功能？ 请参阅我们的[发行说明](/visualstudio/releasenotes/vs2017-relnotes)。

准备安装？ 我们将逐步引导你完成安装。

## <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>第 1 步 - 确保计算机支持 Visual Studio

开始安装 Visual Studio 前：

1. 查看[系统要求](/visualstudio/productinfo/vs2017-system-requirements-vs)。 这些要求有助于了解计算机是否支持 Visual Studio 2017。
2. 应用最新的 Windows 更新。 这些更新可确保计算机包含最新的安全更新程序和 Visual Studio 所需的系统组件。
3. 重新启动。 重新启动可确保挂起的任何安装或更新都不会影响 Visual Studio 安装。
4. 释放空间。 通过运行磁盘清理应用程序等方式，从 %SystemDrive% 删除不需要的文件和应用程序。

若对如何并行运行旧版 Visual Studio 和 Visual Studio 2017 有疑问，请参阅 [Visual Studio 兼容性详细信息](/visualstudio/productinfo/vs2017-compatibility-vs#compatibility-with-previous-releases)。

## <a name="step-2---download-visual-studio"></a>第 2 步 - 下载 Visual Studio

接下来，下载 Visual Studio 引导程序文件。 为此，请单击下面的按钮，选择所需的 Visual Studio 2017 版本，单击“保存”，然后单击“打开文件夹”。

 > [!div class="button"]
 > [下载 Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
<br/>

## <a name="step-3---install-the-visual-studio-installer"></a>第 3 步 - 卸载 Visual Studio 安装程序

然后，运行引导程序文件以安装 Visual Studio 安装程序。 这个新的轻型安装程序包括安装和自定义 Visual Studio 2017 所需的一切。

1. 在“下载”文件夹中，双击与下列文件之一匹配或类似的引导程序文件：

   * 对于 Visual Studio Enterprise，请运行 **vs_enterprise.exe**
   * 对于 Visual Studio Professional，请运行 **vs_professional.exe**
   * 对于 Visual Studio Community，请运行 **vs_community.exe**  <br><br>

   如果收到用户帐户控制通知，请单击“是”。

2. 我们会要求确认 Microsoft [许可条款](https://visualstudio.microsoft.com/license-terms/)和 Microsoft [隐私声明](https://privacy.microsoft.com/privacystatement)。 单击 **“继续”**。

   ![许可条款和隐私声明](media/vs2017-privacy-and-license-terms.PNG "Microsoft 许可条款和隐私声明")

## <a name="step-4---select-workloads"></a>第 4 步 - 选择工作负载

安装该安装程序后，可以通过选择所需的功能集或工作负载来使用该程序自定义安装。 操作方法如下。

1. 在“安装 Visual Studio”屏幕中找到所需的工作负载。

   ![从 Visual Studio 2017 设置对话框中选择工作负载](../install/media/install-visual-studio-community.png)

     例如，选择“.NET 桌面开发”工作负载。 它附带默认核心编辑器，该编辑器针对超过 20 种语言提供基本代码编辑支持，能够打开和编辑任意文件夹中的代码（而无需使用项目），还提供集成的源代码管理。

2. 选择所需的工作负载后，单击“安装”。

    接下来，会出现多个显示 Visual Studio 安装进度的状态屏幕。

3. 安装完新的工作负载和组件后，单击“启动”。

> [!TIP]
> 在安装之后，可以随时安装最初未安装的工作负荷或组件。 如果已打开 Visual Studio，请转到“工具” > “获取工具和功能...”，这会打开 Visual Studio 安装程序。 或者，从“开始”菜单打开“Visual Studio 安装程序”。 在此处可以选择要安装的工作负荷或组件，然后单击“修改”。

## <a name="step-5---select-individual-components-optional"></a>第 5 步 - 逐个选择组件（可选）

如果不想使用工作负载功能来自定义 Visual Studio 安装，可以改为逐个安装组件。 若要选择单个组件，请从 Visual Studio 安装程序中单击“单个组件”选项，选择所需项，然后按照提示操作。

  ![Visual Studio 2017 - 安装各个组件](media/vs2017-components.PNG "安装 Visual Studio 各个组件")

## <a name="step-6---install-language-packs-optional"></a>第 6 步 - 安装语言包（可选）

默认情况下，安装程序首次运行时会尝试匹配操作系统语言。 若要以所选语言安装 Visual Studio 2017，请从 Visual Studio 安装程序中单击“语言包”选项，并按提示操作。

  ![Visual Studio 2017 - 安装语言包](media/vs2017-languages.PNG "安装 Visual Studio 语言包")

### <a name="change-the-installer-language-from-the-command-line"></a>从命令行更改安装程序语言

更改默认语言的另一种方法是从命令行运行安装程序。 例如，可以通过运行以下命令来强制安装程序用英语运行：`vs_installer.exe --locale en-US`。 安装程序下一次运行时会记住此设置。 安装程序支持以下语言标记：zh-cn、zh-tw、cs-cz、en-us、es-es、fr-fr、de-de、it-it、ja-jp、ko-kr、pl-pl、pt-br、ru-ru 和 tr-tr。

## <a name="step-7---change-the-installation-location-optional"></a>第 7 步 - 更改安装位置（可选）

**15.7 中的新增功能**：现在可减少系统驱动器上 Visual Studio 的安装量。 可以选择将下载缓存、共享组件、SDK 和工具移动到不同驱动器，并将 Visual Studio 安装在其运行速度最快的驱动器上。

  ![Visual Studio 2017 - 更改安装位置](media/installation-options-by-location.png "更改安装位置")

有关详细信息，请参阅[更改 Visual Studio 中的安装位置](change-installation-locations.md)页。

## <a name="step-8---start-developing"></a>第 8 步 - 开始开发

1. 在 Visual Studio 安装完成后，单击“启动”按钮，开始使用 Visual Studio 进行开发。

2. 单击“文件”，然后单击“新建项目”。

3. 选择一种项目类型。

   例如，若要[生成 C++ 应用](../ide/getting-started-with-cpp-in-visual-studio.md)，请单击“已安装”，展开“Visual C++”，再选择要生成的 C++ 项目类型。

   若要[生成 C# 应用](../get-started/csharp/tutorial-wpf.md)，请单击“已安装”，展开“Visual C#”，再选择要生成的 C# 项目类型。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>请参阅

* [更新 Visual Studio 2017](update-visual-studio.md)
* [修改 Visual Studio 2017](modify-visual-studio.md)
* [卸载 Visual Studio 2017](uninstall-visual-studio.md)
* [创建 Visual Studio 2017 的脱机安装](create-an-offline-installation-of-visual-studio.md)
* [使用命令行参数安装 Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md)
* [安装 Visual Studio for Mac](/visualstudio/mac/installation)