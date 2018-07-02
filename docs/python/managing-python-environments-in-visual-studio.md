---
title: 管理 Python 环境和解释器
description: 使用 Python 环境窗口来管理全局、虚拟和 Conda 环境、安装 Python 解释器和包以及将环境分配给 Visual Studio 项目。
ms.date: 05/22/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: d8c500b5f10f424cf60d92fd75a77e0ccb55866e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34477569"
---
# <a name="how-to-create-and-manage-python-environments-in-visual-studio"></a>如何在 Visual Studio 中创建和管理 Python 环境

Python 环境是在其中运行 Python 代码的上下文，它包括全局、虚拟和 Conda 环境。 环境由解释器、库（通常是 Python 标准库）以及一组已安装的包组成。 这些组成部分共同确定哪些语言结构和语法有效、哪些操作系统功能可访问以及哪些包可使用。

在 Windows 上的 Visual Studio 中，你可在 [Python 环境](#the-python-environments-window)窗口（如本文中所述）中管理这些环境并选择其中一个作为新项目的默认环境。 对于任何给定的项目，也可以[选择特定环境](selecting-a-python-environment-for-a-project.md)而不使用默认环境。

**注意**：如果不熟悉 Visual Studio 中的 Python，请参阅以下文章了解必要背景：

- [在 Visual Studio 中使用 Python](overview-of-python-tools-for-visual-studio.md)
- [安装针对 Visual Studio 的 Python 支持](installing-python-support-in-visual-studio.md)

另请注意，你无法管理使用“文件” > “打开” > “文件夹”命令仅以文件夹方式打开的 Python 代码的环境。 但是，[从现有代码创建 Python 项目](quickstart-01-python-in-visual-studio-project-from-existing-code.md)即可享受 Visual Studio 的环境功能。

如果想在环境中安装包，请参阅[“包”选项卡引用](python-environments-window-tab-reference.md#packages-tab)。

## <a name="types-of-environments"></a>环境类型

### <a name="global-environments"></a>全局环境

每个 Python 安装（例如，Python 2.7、Python 3.6 和 Anaconda 4.4.0 等，请参阅[选择并安装 Python 解释器](installing-python-interpreters.md)）都会维护自己的全局环境。 每个环境都包括特定的 Python 解释器、其标准库和一组预安装包。 将包安装到全局环境使其适用于使用此环境的所有项目。 如果环境位于文件系统的保护区域内（例如，`c:\program files` 内），则安装包时需要管理员权限。

全局环境适用于计算机上的所有项目。 在 Visual Studio 中，选择一个全局环境作为默认环境，此环境可用于所有项目，除非为项目专门选择了其他环境。 有关详细信息，请参阅[选择项目环境](selecting-a-python-environment-for-a-project.md)。

### <a name="virtual-environments"></a>虚拟环境

由于安装到全局环境中的包适用于使用此环境的所有项目，因此当两个项目需要不兼容的包或同一个包的不同版本时，可能会发生冲突。 虚拟环境通过使用全局环境中的解释器和标准库但将其自身包存储在独立文件夹来避免此类冲突。

在 Visual Studio 中，可针对项目子文件夹中存储的特定项目创建虚拟环境。 Visual Studio 提供基于虚拟环境生成 `requirements.txt` 的命令，简化了在其他计算机上重新创建环境的过程。 有关详细信息，请参阅[使用虚拟环境](selecting-a-python-environment-for-a-project.md#using-virtual-environments)。

### <a name="conda-environments"></a>Conda 环境

Conda 环境是使用 `conda` 工具或通过 Visual Studio 2017 版本 15.7 及更高版本中的集成式 Conda 管理创建的环境。 （需要 Anaconda 或 Miniconda；Anaconda 可通过 Visual Studio 安装程序使用，请参阅[安装 - Visual Studio 2017](installing-python-support-in-visual-studio.md#visual-studio-2017)。）

> [!Note]
> 为获得 Conda 环境的最佳使用结果，请使用 Conda 4.4.8 或更高版本（Conda 版本与 Anaconda 版本不同）。 从 Visual Studio 2017 安装程序安装 Anaconda 5.1

若要查看 Conda 版本、Conda 环境的存储位置以及其他信息，请在 Anaconda 命令提示符（即路径中包含 Anaconda 的命令提示符）运行 `conda info`：

```cli
conda info
```

conda 环境文件夹如下所示：

```output
       envs directories : c:\anaconda3\envs
                          C:\Users\user\AppData\Local\conda\conda\envs
                          C:\Users\user\.conda\envs
```

由于未使用项目存储 Conda 环境，这些环境与全局环境的功能类似。 例如，将新包安装到 Conda 环境，从而使该包适用于使用此环境的所有项目。

对于 Visual Studio 2017 版本 15.6 及更早版本，可以根据[手动标识现有环境](#manually-identify-an-existing-environment)中所述，通过手动指向 Conda 环境进行使用。

根据下一节所述，Visual Studio 2017 版本 15.7 及更高版本自动检测 Conda 环境，并在“Python 环境”窗口中显示这些环境。

## <a name="the-python-environments-window"></a>“Python 环境”窗口

Visual Studio 了解的环境显示在“Python 环境”窗口中。 若要打开该窗口，请使用以下方法之一：

- 选择“查看” > “其他窗口” > “Python 环境”菜单命令。
- 在“解决方案资源管理器”中，右键单击某项目的“Python 环境”节点，选择“查看所有 Python 环境”：

    ![解决方案资源管理器中的“查看所有环境”命令](media/environments-view-all.png)

在任一情况下，“Python 环境”窗口都显示为解决方案资源管理器的同级选项卡：

![“Python 环境”窗口](media/environments-default-view.png)

如果在列表中看不到预期的环境，请参阅[手动标识现有环境](#manually-identify-an-existing-environment)。

选择列表中的环境会在“概述”选项卡上显示该环境的各种属性和命令。例如，可在上图中看到解释器的位置是 `C:\Python36-32`。 使用环境列表下方的下拉列表可切换到不同的选项卡，例如“包”和“IntelliSense”。 [“Python 环境”窗口选项卡引用](python-environments-window-tab-reference.md)中介绍了这些选项卡。

选择某个环境不会以任何方式激活它。 列表中以粗体显示的默认环境是当前激活的环境，Visual Studio 将其用于任意新项目。 要激活其他环境，请使用“将此作为新项目的默认环境”命令。 在项目的上下文中，可以始终激活不同的环境。 有关详细信息，请参阅[选择项目环境](selecting-a-python-environment-for-a-project.md)。

所列出的每个环境右侧的控件可为此环境打开交互窗口。 （在 Visual Studio 2017 15.5 及更早版本中，可能还会显示另一个控件，用于刷新此环境的 IntelliSense 数据库。 请参阅[“环境”窗口选项卡引用](python-environments-window-tab-reference.md#intellisense-tab)，获取有关数据库的详细信息）。

> [!Tip]
> 如果将“Python 环境”窗口展开到足够宽，可以获得更加完整的环境视图，从而可使操作更加便捷。
>
> ![“Python 环境”窗口扩展后的视图](media/environments-expanded-view.png)

> [!Note]
> 尽管 Visual Studio 遵循系统-站点-包选项，但它没有提供从 Visual Studio 中更改它的方法。

|   |   |
|---|---|
| ![视频的摄像机图标](../install/media/video-icon.png "观看视频") | 有关 Visual Studio 中的 Python 环境，请[观看视频（Microsoft 虚拟学院）](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567)（2 分 35 秒）。|

### <a name="what-if-no-environments-appear"></a>如果未出现环境该怎么办？

如果未出现任何环境，这意味着 Visual Studio 在标准位置中未能检测到任何 Python 安装。 例如，你可能已安装 Visual Studio 2017 但清除了 Python 工作负荷的安装程序选项中的所有解释器选项。 同样地，你可能已安装 Visual Studio 2015 或更早版本，但未手动安装解释器（请参阅[安装 Python 解释器](installing-python-interpreters.md)）。

如果你知道计算机上有一个 Python 解释器，但 Visual Studio（任何版本）未检测到它，则使用“+ 自定义...”命令来手动指定其位置。 请参阅下一节[手动标识现有环境](#manually-identify-an-existing-environment)。

> [!Tip]
> Visual Studio 可检测现有解释器的更新，如使用 python.org 的安装程序将 Python 2.7.11 升级到 2.7.14。在安装过程中，较旧的环境从“Python 环境”列表消失后，更新才会显示在其位置上。
>
> 但是，如果你使用文件系统手动移动解释器及其环境，则 Visual Studio 不会知道新位置。 有关更多信息，请参阅[移动解释器](installing-python-interpreters.md#moving-an-interpreter)。

<a name="manually-identifying-an-existing-environment></a>

## <a name="manually-identify-an-existing-environment"></a>手动标识现有环境

使用以下步骤来标识安装在非标准位置的环境（包括 Visual Studio 2017 版本 15.6 及更早版本中的 Conda 环境）：

1. 选择“Python 环境”窗口中的“+ 自定义”，这将打开“配置”选项卡：

    ![新自定义环境的默认视图](media/environments-custom-1.png)

1. 在“说明”字段中为该环境输入名称。

1. 在“前缀路径”字段中输入或浏览（使用 **...**）到解释器的路径。

1. 如果 Visual Studio 监测到此位置存在 Python 解释器（如下所示的 conda 环境的路径），它将启用“自动检测”命令。 选择 “自动检测”填写剩余的字段。 你还可以手动填写这些字段。

    ![启用“自动检测”命令](media/environments-custom-2.png)

    ![使用“自动检测”后填写环境字段](media/environments-custom-3.png)

1. 如果字段包含所需的值，则选择“应用”保存配置。 现在你可以在 Visual Studio 中使用像任何其他环境一样的环境了。

1. 如果需要删除手动标识的环境，请在“配置”选项卡上选择“删除”命令。自动检测环境不提供此选项。 有关更多信息，请参阅[配置选项卡](python-environments-window-tab-reference.md#configure-tab)。

## <a name="create-a-conda-environment"></a>创建 Conda 环境

Visual Studio 2017 版本 15.7 和更高版本。

1. 选择“Python 环境”窗口中的“+ 创建 Conda 环境”，这将打开“新建 Conda 环境”选项卡：

    ![创建新 Conda 环境的选项卡](media/environments-conda-1.png)

1. 在“名称”字段中输入环境名称，在“Python”字段中选择基础 Python 解释器，然后选择“创建”。

1. “输出”窗口显示新环境的创建进度，创建完成后将显示几条 CLI 指令：

    ![成功创建 Conda 环境](media/environments-conda-2.png)

1. 如[为项目选择环境](selecting-a-python-environment-for-a-project.md)中所述，在 Visual Studio 中，可以像激活任何其他环境一样，为项目激活 Conda 环境。

1. 若要在环境中安装包，请使用[包选项卡](python-environments-window-tab-reference.md#packages-tab)。

## <a name="see-also"></a>请参阅

- [安装 Python 解释器](installing-python-interpreters.md)
- [为项目选择解释器](selecting-a-python-environment-for-a-project.md)
- [对依赖项使用 requirements.txt](managing-required-packages-with-requirements-txt.md)
- [搜索路径](search-paths.md)
- [“Python 环境”窗口参考](python-environments-window-tab-reference.md)