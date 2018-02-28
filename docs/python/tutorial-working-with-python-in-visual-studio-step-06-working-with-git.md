---
title: "在 Visual Studio 中使用 Python - 第 6 步：使用 Git | Microsoft Docs"
description: "在 Visual Studio 中使用 Python 的核心教程的第 6 步，介绍了 Visual Studio 的 Git 相关功能。"
ms.custom: 
ms.date: 01/16/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: eb39d8807deb0c08b12b04128365c584d9bd8251
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="step-6-working-with-git"></a>步骤 6：使用 Git

**上一步：[安装程序包和管理 Python 环境](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)**

Visual Studio 提供与本地 Git 存储库以及驻留在 GitHub 和 Visual Studio Team Services 等服务上的存储库的直接集成。 集成包括克隆存储库、提交更改和管理分支。

本主题介绍如何为现有项目创建本地 Git 存储库。 有关从远程 Git 存储库创建项目的演练，请参阅[快速入门：在 Visual Studio 中克隆 Python 代码存储库](quickstart-03-python-in-visual-studio-project-from-repository.md)。

1. 在 Visual Studio 中打开项目后，比如[上一步](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)中的项目，右键单击解决方案并选择“将解决方案添加到源代码管理”。 Visual Studio 会创建一个包含项目代码的本地 Git 存储库，Git 相关控件也出现在 Visual Studio 窗口底部。 控件显示挂起的提交、更改、存储库名称和分支。 将鼠标悬停在控件上可查看附加信息。

  ![将鼠标悬停在 Visual Studio 窗口中的 Git 控件上时显示附加信息](media/working-with-git-01.png)

1. 选择存储库标头时，还会显示包含各种可用 Git 选项的“团队资源管理器”窗口。 选择 Push 标头时显示的“同步”窗格提供用于发布到远程存储库的选项。

  ![创建本地存储库后 Visual Studio 中的团队资源管理器](media/working-with-git-02.png)

1. 选择“更改”以查看未提交的更改并在需要时提交它们。

  ![Visual Studio 中显示未提交更改的团队资源管理器](media/working-with-git-03.png)

1. 选择“分支”以检查分支并执行合并和变基操作：

  ![Visual Studio 中显示分支的团队资源管理器](media/working-with-git-04.png)

1. 使用本地存储库时，提交的更改直接进入存储库。 如果已连接到远程存储库，则选择标头，再选择“同步”以切换到“同步”部分，然后处理此处显示的命令。

## <a name="going-deeper"></a>深入了解

有关使用 Git 的更广泛的教程，请参阅[与 Visual Studio 2017 和 VSTS Git 共享代码](/vsts/git/share-your-code-in-git-vs-2017)

## <a name="tutorial-review"></a>教程回顾

恭喜你完成有关 Visual Studio 中 Python 的这一教程。 在本教程中，已了解如何：

- 创建项目和查看项目内容。
- 使用代码编辑器和运行项目。
- 使用交互窗口开发新代码，并将该代码轻松复制到编辑器中。
- 在 Visual Studio 调试器中运行已完成的程序。
- 安装程序包和管理 Python 环境
- 使用 Git 存储库中的代码

从此处了解概念和操作说明指南，其中包括：

- [创建适用于 Python 的 C++ 扩展](working-with-c-cpp-python-in-visual-studio.md)
- [发布到 Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md)
- [分析](profiling-python-code-in-visual-studio.md)
- [单元测试](unit-testing-python-in-visual-studio.md)
