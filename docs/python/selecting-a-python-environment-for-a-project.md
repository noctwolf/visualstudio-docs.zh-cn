---
title: "为项目选择环境 | Microsoft Docs"
description: "在 Visual Studio 解决方案资源管理器中，可以分配一个特定的 Python 解释器（环境）以始终用于任何给定项目，忽略默认环境。 还可以创建和管理虚拟环境。"
ms.custom: 
ms.date: 02/20/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 6f422cc60638b7eed4a5b42516e7496c4a6f6209
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2018
---
# <a name="selecting-a-python-interpreter-and-environment-for-use-in-a-project"></a>选择在项目中使用的 Python 解释器和环境

Python 项目中的所有代码均在特定环境的上下文中运行。 Visual Studio 还将该环境用于调试、导入和成员完成情况、语法检查以及任何需要环境的其他任务。

Visual Studio 中所有新的 Python 项目最初都被配置为使用默认的全局环境，它出现在“解决方案资源管理器”的“Python 环境”节点下：

![“解决方案浏览器”中显示的全局默认 Python 环境](media/environments-project.png)

你可以为项目提供其他可用环境，包括虚拟环境。 在任何给定时间内，只能激活一个环境。

## <a name="using-global-environments"></a>使用全局环境

要为项目提供可用的特定全局环境（包括[手动标识的](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment) conda 环境），请右键单击“Python 环境”节点，并选择“添加/删除 Python 环境…”。从显示的列表中选择所需的环境：

![“添加/删除 Python 环境”对话框](media/environments-add-remove.png)

一旦选择“确定”，所有选择的环境都将显示在“Python 环境”节点中。 当前激活的环境以粗体显示：

![“解决方案浏览器”中显示的多个 Python 环境](media/environments-project-multiple.png)

若要激活其他环境，右键单击环境名称，并选择“激活环境”。 你的选择将保存在项目中，当你在将来打开该项目，环境就会被激活。

如果在“添加/删除 Python 环境”对话框中清除所有选项，Visual Studio 将激活全局默认环境。

## <a name="using-virtual-environments"></a>使用虚拟环境

虚拟环境是特定 Python 解释器和一组特定库的独特组合，它与其他全局环境以及 conda 环境不同。 当你在项目中有特定需求，并且不希望修改其他环境来满足这些需求时，通常会使用虚拟环境。

将虚拟环境添加到项目后，它将出现在“Python 环境”窗口中，可像激活任何其他环境一样激活它，且可以管理其包。

请注意，虚拟环境的一个缺点是，它们包含硬编码文件路径，因此无法轻松地进行共享或传输到其他开发计算机上。 幸运的是，可以使用 `requirements.txt` 文件让项目接收方可以轻松还原环境。 有关详细信息，请参阅[使用 requirements.txt 管理所需的包](managing-required-packages-with-requirements-txt.md)。

### <a name="activating-an-existing-virtual-environment"></a>激活现有的虚拟环境

如果你已经在其他地方创建了虚拟环境，可以按以下方式为项目激活它：

1. 在“解决方案资源管理器”中，右键单击“Python 环境”并选择“添加现有虚拟环境...”。

1. 在出现的“浏览”对话框中，导航到包含虚拟环境的文件夹并选中，然后选择“确定”。 如果 Visual Studio 在该环境中检测到 `requirements.txt` 文件，它会询问是否安装这些包。

1. 稍后，虚拟环境会出现在“解决方案资源管理器”中的“Python 环境”节点下。 默认情况下不会激活虚拟环境，因此请右键单击它并选择“激活环境”。

### <a name="creating-a-virtual-environment"></a>创建虚拟环境

可以直接从 Visual Studio 创建一个新的虚拟环境，如下所示：

1. 在“解决方案资源管理器”中，右键单击“Python 环境”并选择“添加虚拟环境...”，将会打开以下对话框：

    ![创建虚拟环境](media/environments-add-virtual-1.png)

1. 在“虚拟环境位置”字段中，指定虚拟环境的路径。 如果仅指定一个名称，则会在当前项目中在具有该名称的子文件夹中创建虚拟环境。

1. 选择一个环境作为基础解释器，并选择“创建”。 Visual Studio 会在配置环境和下载任何必要的包时显示一个进度栏。 此时虚拟环境会显示在包含项目的“Python 环境”窗口中。

1. 默认情况下不会激活虚拟环境。 若要为项目激活虚拟环境，请右键单击该项目，然后选择“激活环境”。

> [!Note]
> 如果位置路径标识一个现有的虚拟环境，Visual Studio 会自动检测基础解释器（使用环境 `lib` 目录中的 `orig-prefix.txt` 文件）并将“创建”按钮更改为“添加”。
>
> 添加虚拟环境时，如果 `requirements.txt` 文件存在，“添加虚拟环境”对话框会显示一个自动安装包的选项，从而可以轻松地在另一台计算机上重新创建环境：
>
> ![使用 requirements.txt 创建虚拟环境](media/environments-requirements-txt.png)
>
> 无论采用哪种方式，结果都与使用“添加现有的虚拟环境…”命令相同。

### <a name="remove-a-virtual-environment"></a>删除虚拟环境

1. 在“解决方案资源管理器”中，右键单击虚拟环境，然后选择“删除”。

1. Visual Studio 会询问是否移除或删除虚拟环境。 选择“移除”，使其对项目不可用，但在文件系统上保留它。 选择“删除”，从项目中移除环境，并从文件系统中删除它。 基础解释器不受影响。

## <a name="viewing-installed-packages"></a>查看已安装的包

在“解决方案资源管理器”中，展开特定环境节点以快速查看在该环境中安装的包（也就是说，你可以激活环境时在代码中导入和使用这些包）：

![解决方案资源管理器中某环境的 Python 包](media/environments-installed-packages.png)

要安装新的包，右键单击环境并选择“安装 Python 包…”以切换到“Python 环境”窗口中的“包”选项卡。 输入搜索词（通常是包名称），Visual Studio 将显示匹配的包。

在 Visual Studio 中，从 [Python 包索引 (PyPI)](https://pypi.python.org/pypi) 下载包（及其依赖项），还可以在其中搜索可用的包。 Visual Studio 的状态栏和输出窗口显示有关安装的信息。 若要卸载包，请右键单击它，选择“删除”。

请注意，显示的项未必总准确，且安装和卸载可能不可靠或不可用。 Visual Studio 使用 pip 程序包管理器（如果可用），并且需要时会下载并安装它。 Visual Studio 还可以使用 easy_install 程序包管理器。 也会显示使用 `pip` 或 `easy_install` 从命令行安装的包。

另请注意，Visual Studio 目前不支持使用 `conda` 将包安装到 conda 环境中。 而是使用命令行中的 `conda`。

> [!Tip]
> 当包中包含用于 `*.pyd` 文件中本机组件的源代码时，pip 无法安装包，这种情况很常见。 如果没有安装要求的 Visual Studio 版本，pip 无法编译这些组件。 在此情况下显示的错误消息是：`error: Unable to find vcvarsall.bat`。 `easy_install` 通常能够下载预编译二进制文件，可从 [http://aka.ms/VCPython27](http://aka.ms/VCPython27) 下载较旧的 Python 版本适用的编译器。 有关详细信息，请参阅 Python 工具团队博客上的[How to deal with the pain of "unable to find vcvarsallbat"](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/11/unable-to-find-vcvarsall-bat/)（如何处理“找不到 vcvarsallbat”问题）。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中管理 Python 环境](managing-python-environments-in-visual-studio.md)
- [对依赖项使用 requirements.txt](managing-required-packages-with-requirements-txt.md)
- [搜索路径](search-paths.md)
- [Python 环境窗口引用](python-environments-window-tab-reference.md)