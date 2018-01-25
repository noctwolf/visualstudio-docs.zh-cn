---
title: "快速入门：使用 Visual Studio 中的 Cookiecutter 创建 Python 项目 | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: quickstart
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: dfe00af70cdbfbe9c583d15fc5431dc7a85d8276
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2018
---
# <a name="quickstart-create-a-project-from-a-cookiecutter-template"></a>快速入门：从 Cookiecutter 模板创建项目

[在 Visual Studio 2017 中安装 Python 支持](installing-python-support-in-visual-studio.md)后，就可以从 Cookiecutter 模板轻松创建新项目，其中包括许多发布到 GitHub 的模板。 [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) 可提供图形用户界面，用于发现模板、输入模板选项以及创建项目和文件。 Cookiecutter 在 Visual Studio 2017 中随附，在 Visual Studio 早期版本中可单独安装。

1. 在本快速入门教程中，首先安装 Anaconda3 Python 分发版本，其中包括此处所示的 Cookiecutter 模板必需的 Python 程序包。 运行 Visual Studio 安装程序，选择“修改”，展开右侧的“Python 开发”选项，选择“Anaconda3”（32 位或 64 位均可）。 请注意，安装可能需要一些时间，具体取决于 Internet 速度，但这是安装所需程序包最简单的方法。

1. 启动 Visual Studio。

1. 选择“文件”>“新建”>“从 Cookiecutter...”。此命令会在 Visual Studio 中打开一个窗口，可在窗口中浏览模板。 

    ![从 Cookiecutter 模板新建项目](media/projects-from-cookiecutter1.png)

1. 选择“Microsoft/python-sklearn-classifier-cookiecutter”模板，然后选择“下一步”。 （第一次使用 Cookiecutter 时，该过程可能需要几分钟。）

1. 接下来，在“创建到”字段中设置新项目的位置，然后选择“创建”。

    ![第二步使用 Cookiecutter, 设置项目属性](media/projects-from-cookiecutter2.png)

1. 该过程完成后，显示“已成功创建文件”消息。 选择“在解决方案资源管理器中打开”命令打开项目。

1. 按 Ctrl+F5 或选择“调试”>“开始执行(不调试)”运行程序。 

    ![python-sklearn-classifier-cookiecutter 模板项目的输出](media/projects-from-cookiecutter4.png)

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [教程：在 Visual Studio 中使用 Python](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>请参阅

- [使用 Cookiecutter 扩展](cookiecutter.md)
- [为现有 Python 解释器创建环境](managing-python-environments-in-visual-studio.md#creating-an-environment-for-an-existing-interpreter)。
- [在 Visual Studio 2015 及更早版本中安装 Python 支持](installing-python-support-in-visual-studio.md)。
- [安装位置](installing-python-support-in-visual-studio.md#install-locations)。
